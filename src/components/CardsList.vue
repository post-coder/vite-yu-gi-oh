<script>
import {store} from '../store'

import CardItem from './CardItem.vue';

export default {
    name: 'CardsList',

    data() {
        return {
            store,
        }
    },

    components: {
        CardItem,
    }
}
</script>

<template>
    <h2>Carte</h2>

    <ul id="cards-list">
        <CardItem v-for="currentCard in store.cards" :card="currentCard"></CardItem>
    </ul>
</template>

<style lang="scss">
@use '../styles/variables' as *;

#cards-list {
    display: flex;
    flex-flow: wrap;
    gap: $cardListGap;

    
}

</style>
