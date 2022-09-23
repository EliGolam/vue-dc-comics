<template>
<main class="page-main">
    <div class="placeholder container">
        <p class="placeholder-content">Content Goes Here</p>
        <p class="coming-soon">Coming Soon...</p>
    </div>

    <ShopDC /> 
</main>
</template>

<script>
import ShopDC from "./ShopDC.vue";

export default {
    name: "PageMain",
    components: {
        ShopDC,
    }
}
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";

@mixin placeholder {
    display: flex;
    justify-content: center;
    align-items: center;
    color: $clr-light;
    text-align: center;
    position: relative;

    .placeholder-content {
        letter-spacing: .6rem;
        font-size: $fs-3;
        font-weight: $fw-bold;
    }

    .coming-soon {
        font-size: $fs-3;
        color: rgba($clr-light, .5);
        position: absolute;
            bottom: 30%;
            right: 22%;

        transform: rotate(-20deg)
    }
    
}

.placeholder {
    @include placeholder();
    min-height: 8rem;
    margin: 0 auto;
}

.page-main {
    background-color: $clr-secondary;
}
</style>