<script>
import axios from 'axios';
import {store} from './store';

export default {
  data() {
    return {

      store,
    }
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
  
</template>

<style lanc="scss">

</style>
