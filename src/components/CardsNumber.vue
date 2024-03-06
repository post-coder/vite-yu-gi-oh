<script>
import {store } from '../store';

export default {
    name: 'CardsNumber',

    data() {
        return  {
            store,
        }
    },

}

</script>
 
<template>
    
    <div>
        Numero di carte: {{ store.numberOfCards }}
    </div>

</template>

<style lang="scss">



</style>