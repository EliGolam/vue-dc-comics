<template>
<nav>
    <h3 class="nav-title">{{ navTitle }}</h3>

    <ul class="nav-list">
        <li v-for="link in navList" :key="link" class="nav-item">
            <a :href="link.link">{{ link.name }}</a>
        </li>
    </ul>
</nav>
</template>


<script>
export default {
    name: "NavList",
    props: {
        navTitle: String,
        navList: Array,
    }
}
</script>


<style lang="scss" scoped>
@import "../styles/variables.scss";

.nav-item {
    color: rgba($clr-light, .5);
    cursor: hover;

    @media (hover: hover) {
        &:hover {
            color: $clr-light;
        }
    }
}
</style>