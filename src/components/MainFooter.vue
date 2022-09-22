<template>
<footer class="main-footer">
    <div class="container">
        <div class="icon-container">
            <figure class="icon" v-for="icon in icons" :key="icon" >
                <img :src="`${publicPath}${getIcon(icon)}`" :alt="getIconDescription(icon)">
                <figcaption>{{getIconDescription(icon)}}</figcaption>
            </figure>

        </div>
    </div>
</footer>  
</template>

<script>
export default {
    name: "MainFooter",

    data() {
        return {
            publicPath: process.env.BASE_URL,
            IMG_FORMAT: ".png",
            IMG_PATH: "assets/img/",
            IMG_PREFIX: "buy-comics-",

            icons: ["digital-comics", "merchandise", "shop-locator", "subscriptions"],
        }
    },

    methods: {
        getIcon(icon) {
            const source = (this.IMG_PATH + this.IMG_PREFIX + icon + this.IMG_FORMAT);
            // console.log("Test MainFooter Icon Sources: ", source);
            return source;
        }, 

        getIconDescription(icon) {
            const alt = icon.split('-');

            for(let i = 0; i < alt.length; i++) {
                alt[i] = alt[i][0].toUpperCase() + alt[i].substring(1);
            }

            return alt.join(" ")
        }
    }, 

    mounted() {
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";


.main-footer {
    background-color: $clr-primary;
    padding: 2rem;
}

.icon-container {
    display: flex;
    justify-content: space-between;
}

.icon {
    display: flex;
    align-items: center;

    color: $clr-light;
}
</style>