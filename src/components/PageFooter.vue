<template>
<footer>
    <div class="container footer-body">

        <div class="navigation">
            <h2 class="visually-hidden">Bottom Page Navigation</h2>

            <NavList v-for="title in navTitles" :key="title" 
                :navTitle="title" 
                :navList="navLinks[title]"/>
        </div>

        <img src="../assets/img/dc-logo-bg.png" alt="">
    </div>

    <FooterEnd :socialLinks="socials"/>

</footer>  
</template>

<script>
import NavList from '@/utility-components/NavList.vue';
import FooterEnd from '@/utility-components/FooterEnd.vue';


export default {
    name: "PageFooter",
    components: {
        NavList,
        FooterEnd
    },

    props: {
        navLinks: Object,
        socials: Array,
    },

    data () {
        return {
            navTitles: undefined,
        }
    },

    methods: {
        getTitles() {
            return Object.keys( this.navLinks );
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
    $height: 25rem;

    background: url("../assets/img/footer-bg.jpg");
    color: $clr-light;
    overflow: hidden;
    position: relative;
        z-index: 0;

    .footer-body {
        overflow: hidden;
        padding: 3rem 0;
    }
    
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
            z-index: -1;
    }
}
</style>