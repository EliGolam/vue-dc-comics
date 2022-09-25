<template>
<section class="container card-container">

    <h2 class="section-title">Current Series</h2>

    <CardItem v-for="(card,index) in cardsData" :key="index"
        :cardTitle="card.series"
        :cardBody="getBody(index)"
        :cardImg="getImage(card)"
        :cardAlt="getDescription(index)"
        class="card"
        />
</section>
</template>

<script>
import CardItem from "@/utility-components/CardItem.vue";

export default {
    name: "CardContainer",

    components: {
        CardItem,
    }, 

    props: {
        cardsData: Array,
    },

    data() {
        return {
            publicPath: process.env.BASE_URL,
            IMG_PATH: "assets/img/",
        }
    },

    methods: {
        getDescription(cardIndex) {
                const { series, type } = this.cardsData[cardIndex];
                return `Cover of the ${type}: ${series}`
        },

        getBody(cardIdx) {
            const { type, price } = this.cardsData[cardIdx];
            return [type, price];
        }, 

        getImage(card) {
            const source = this.publicPath + this.IMG_PATH + card.thumb;
            return source;
        }
    },
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";

.card-container {
    $r-gap: 3.5rem;
    $c-gap: 1rem;

    display: flex;
    flex-wrap: wrap;
    row-gap: $r-gap;
    column-gap: $c-gap;

    margin: 5rem auto;
    position: relative;

    .section-title {
        position: absolute;
        top: -5rem;
        transform: translateY(-50%);
        background-color: $clr-primary;
        padding: .2rem .8rem;
        border-radius: .3em;
        color: $clr-light;
    }

    .card {
        width: calc(100% / 2 - $c-gap);
        aspect-ratio: 1 / 1.5;

        @media only screen and (min-width: $sm-breakpoint) {
            width: calc(100% / 3 - $c-gap);
        }

        @media only screen and (min-width: $md-breakpoint) {
            width: calc(100% / 6 - $c-gap);
        }
    }
}




</style>