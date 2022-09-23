<template>
<div class="footer-end">
    <div class="container">
        <div class="cta">
            <button>Sign-up Now</button>

            <p>Follow Us</p>
        </div>

        <div class="socials">
            <IconLink v-for="icon in icons" :key="icon" 
                :link="'#'"
                :logoPath="`${getIcon(icon)}`"
                :description="getIconDescription(icon)"
            />
        </div>
    </div>
</div>  
</template>

<script>
import IconLink from '@/utility-components/IconLink.vue';

export default {
    name: "FooterEnd",
    components: { 
        IconLink, 
    },

    props: {
        socialLinks: Array,
    },

    data() {
        return {
            publicPath: process.env.BASE_URL,
            IMG_FORMAT: ".png",
            IMG_PATH: "assets/img/",
            IMG_PREFIX: "footer-",
            icons: ["facebook", "twitter", "youtube", "pinterest", "periscope"],
        };
    },
    methods: {
        getIcon(icon) {
            const source = (this.IMG_PATH + this.IMG_PREFIX + icon + this.IMG_FORMAT);
            // console.log("Test ShopDC Icon Sources: ", source);
            return this.publicPath + source;
        },

        getIconDescription(icon) {
            const alt = icon.split("-");
            for (let i = 0; i < alt.length; i++) {
                alt[i] = alt[i][0].toUpperCase() + alt[i].substring(1);
            }
            return alt.join(" ");
        },
    },
    
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";

.footer-end {
    background-color: $clr-secondary;
    color: $clr-light;
    padding: 1rem 0;

    .container {
        display: flex;
        align-items: center;
    }

    .cta {
        display: flex;
        flex-grow: 1;
        justify-content: space-between;
        align-items: center;
    }
}
</style>