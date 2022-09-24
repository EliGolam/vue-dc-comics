<template>
<div class="container card-container">
    <CardItem v-for="(card,index) in cardsData" :key="index"
        :cardTitle="card.series"
        :cardBody="getBody(index)"
        :cardImg="getImage(card)"
        :cardAlt="getDescription(index)"
        />
</div>
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

<style>

</style>