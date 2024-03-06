<script>
import CardsNumber from './CardsNumber.vue';

import {store } from '../store';


export default {
    name: 'CardsFilter',

    data() {
        return  {
            store,
        }
    },

    components: {
        CardsNumber,
    },  

}

</script>
 
<template>
    
    <div id="cards-filter">

        <select 
            name="archetype-filter" 
            id="archetype-filter" 
            @change="$emit('filter')"
            v-model="store.filterValue"
        >
            <option 
                v-for="currentArchetype in store.archetypes" 
                :value="currentArchetype.archetype_name"
            >
                {{ currentArchetype.archetype_name }}
            </option>
        </select>

        <CardsNumber></CardsNumber>
    </div>

</template>

<style lang="scss">

#cards-filter {
    display: flex;
    justify-content: space-between;
    align-items: center;

    padding: 24px 0;
    border-bottom: 1px solid #777;

    margin-bottom: 24px;

    select {
        padding: 8px 12px;
    }
}

</style>