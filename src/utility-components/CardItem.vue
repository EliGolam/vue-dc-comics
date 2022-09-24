<template>
<article class="card" :style="getBgImage()">
    <div class="overlay"></div>
    <div class="cardContent">
        <h3 class="title fs-5">{{ cardTitle }}</h3>
        <div class="cardBody fs-6">
            <p>{{cardBody[0]}}</p>
            <p>{{cardBody[1]}}</p>
        </div>
    </div>
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
    
    methods: {
        getBgImage() {
            const background = `background-image: url(${this.cardImg})`;
            return background;
        },
    }
}
</script>


<!-- Style -->
<style lang="scss" scoped>
@import "../styles/variables.scss";

.card {
    text-align: start;
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;
    cursor: pointer;
    
    .overlay {
        position: absolute;
            bottom: 0;
        width: 100%;
        height: 0%;
        background: linear-gradient(
            rgba($clr-secondary, 0),
            rgba($clr-secondary, .3) 25%,
            rgba($clr-secondary, .6),
        );
        transition: height 300ms ease;
    }

    .cardContent {
        position: absolute;
            top: 100%;
        padding: .1rem .3rem;
        width: 100%;
        color: $clr-light;
        overflow: hidden;

        transition: 
            top 300ms ease;

         
        .title {
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;  
        }    

        
        .cardBody {
            display: flex;
            justify-content: space-between;
            transform: translateX(-120%);
            opacity: 0;

            transition: 
                transform 400ms ease 300ms,
                opacity 300ms ease-out 300ms;
        }
    }

    

    &:hover {
        .overlay {
            height: 40%;
        }

        .cardContent {
            top: 65%;
        }

        .title {
            line-height: 1.5em;
            height: 3em;
            white-space: normal;
            overflow: hidden;
        }

        .cardBody {
            transform: translateX(0%);
            opacity: 1;
        }
    }
}
</style>