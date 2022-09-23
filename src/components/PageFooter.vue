<template>
<footer>
    <div class="container">
        <div class="navigation">
            <h2 class="visually-hidden">Bottom Page Navigation</h2>

            <NavList v-for="title in navTitles" :key="title" 
                :navTitle="title" 
                :navList="navElements[title]"/>
        </div>

        <img src="../assets/img/dc-logo-bg.png" alt="">
    </div>
</footer>  
</template>

<script>
import NavList from './NavList.vue';


export default {
    name: "PageFooter",
    components: {
    NavList,
},

    data () {
        return {
            navElements: {
                "DC Comics": ["Characters", "Comics", "Movies", "TV", "Games", "Videos", "News"],
                SHOP: ["Shop DC", "Shop DC Collectibles"],
                DC: ["Terms of Use", "Privacy Policy (New)", "Ad Choices", "Adverstising", "Jobs", "Subscriptions", "Talent Workshops", "CPSC Certificates", "Ratings", "Shop Help", "Contact Us"],
                SITES: ["DC", "MAD Magazine", "DC Kids", "DC Universe", "DC Power Visa"],

            }, 
            navTitles: undefined,
        }
    },

    methods: {
        getTitles() {
            return Object.keys( this.navElements );
        }
    },

    created() {
        this.navTitles = this.getTitles();
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";

footer {
    $height: 20rem;

    background: url("../assets/img/footer-bg.jpg");
    color: $clr-light;
    display: flex;
    align-items: flex-start;
    padding: 3rem 0;

    position: relative;
    overflow: hidden;
    

    .navigation {
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
        width: 30%;

        gap: 2rem;

        max-height: $height;
    }

    img {
        position: absolute;
            top: -6rem;
            right: 0;
    }
}
</style>