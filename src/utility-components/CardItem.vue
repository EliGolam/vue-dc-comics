<template>
<article>
    <h3 class="title">{{ cardTitle }}</h3>
    <img :src="cardImg" :alt="cardAlt" />
    <p>{{cardBody[0]}}</p>
    <p>{{cardBody[1]}}</p>
</article>  
</template>


<!-- Script -->
<script>
export default {
    name: "CardItem",

    props: {
        cardTitle: String,
        cardBody: Array,
        cardImg: String,
        cardAlt: String,
    },
}
</script>


<!-- Style -->
<style lang="scss" scoped>

</style>