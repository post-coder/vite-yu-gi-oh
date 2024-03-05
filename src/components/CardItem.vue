<script>
export default {
    name: 'CardItem',

    data() {
        return {

        }
    },

    props: {
        card: Object,
    }
}
</script>

<template>
 
    <li class="card">
        <img :src="card.card_images[0].image_url" :alt="card.name">
        <strong>
            {{ card.name }}
        </strong>
        <span>
            {{ card.race }}
        </span>
    </li>

</template>

<style lang="scss">
@use '../styles/variables' as *;

.card {
    display: flex;
    flex-flow: column;
    gap: 1em;

    width: calc(100% / 5 - $cardListGap / 5 * 4);

    text-align: center;

    background-color: #d48f38;
}
</style>
