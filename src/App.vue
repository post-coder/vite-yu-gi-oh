<script>
import axios from 'axios';
import {store} from './store';

import CardsList from './components/CardsList.vue';
import AppLoader from './components/AppLoader.vue';
import CardsFilter from './components/CardsFilter.vue';

export default {
  data() {
    return {

      store,
    }
  },

  components: {
    CardsList,
    AppLoader,
    CardsFilter
  },

  created() {

    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0')
      .then(res => {
        console.log('carte', res.data.data)
        this.store.cards = res.data.data;
      });


    // chiamata api per popolare la select di scelta archetipo
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res => {
        console.log('archetipi', res.data)
        this.store.archetypes = res.data;
      })

  },

  methods: {

    filterCards() {
      // console.log('Richiesta di filtro')
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0&archetype=' + this.store.filterValue) 
        .then(res => {
          console.log('Numero di carte', res.data.meta.total_rows)
          this.store.numberOfCards = res.data.meta.total_rows;
          this.store.cards = res.data.data;
      });
    },

  },
}
</script>

<template>
  <AppLoader v-if="! store.cards.length > 0"></AppLoader>
  <div class="container">
    <CardsFilter @filter="filterCards"></CardsFilter>

    <CardsList></CardsList>
  </div>
</template>

<style lanc="scss">

</style>
