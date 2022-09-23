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
}

.icon-container {
    display: flex;
    justify-content: space-between;
    gap: 1rem;
}

.icon {
    // FLEX item
    width: calc(100% / 4);

    // FLEX container
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    padding: 2rem 0;
    cursor: pointer;

    // ANIMATIONS
    transition: transform 200ms ease;

    img {
        max-height: 4rem;
        width: auto;
    }

    figcaption {
        color: $clr-light;
        font-size: $fs-5;
    }

    @media (hover: hover) {
        &:hover {
           transform: scale(1.03) translateY(-20px);
        }
        
    }

    // MEDIA SCREEN BREAKPOINTS
    @media only screen and (min-width: $lg-breakpoint) {
        flex-direction: row;

        img {
            max-height: 6rem;
        }

        figcaption {
            font-size: $fs-4;
        }
    }
}


</style>