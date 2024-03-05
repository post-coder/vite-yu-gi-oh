<script>
import axios from 'axios';
import {store} from './store';

import CardsList from './components/CardsList.vue';
import AppLoader from './components/AppLoader.vue';

export default {
  data() {
    return {

      store,
    }
  },

  components: {
    CardsList,
    AppLoader,
  },

  created() {

    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(res => {
        console.log(res.data.data)
        this.store.cards = res.data.data;
      })

  },
}
</script>

<template>
  <AppLoader v-if="! store.cards.length > 0"></AppLoader>
  <div class="container">

    <CardsList></CardsList>
  </div>
</template>

<style lanc="scss">

</style>
