<template>
<header>
    <h1 class="visually-hidden">DC Comics</h1>
    <div class="header-content container">
        <a href="#">
            <img class="main-logo img-fluid" src="../assets/img/dc-logo.png" alt="DC Logo">
        </a>
        
        <nav class="nav-bar">
            <ul class="nav-list fs-5 fw-bold">
                <!-- <li v-for="(navItem, index) in navList" :key="navItem"
                    class="nav-item" 
                    :class="{ active: index === activeTab }">
                    <a href="#">{{ navItem }}</a>
                </li> -->

                <li v-for="(navItem, index) in navLinks" :key="navItem"
                    class="nav-item"
                    :class="{ active: index === activeTab }"
                    @click="moveToTab(index)">

                    <a :href="navItem.link">{{ navItem.title }}</a>
                </li>
            </ul>
        </nav>
        
    </div>
</header>
</template>


<!-- SCRIPT -->
<script>
export default {
    name: "PageHeader",

    props: {
        navLinks: Array,
    },

    data() {
        return {
            activeTab: 1,
            // navList: ["Characters", "Comics", "Movies", "TV", "Games", "Collectibles", "Videos", "Fans", "News", "Shop"],
        }
    },

    methods: {
        moveToTab(tabIndex) {
            this.activeTab = tabIndex;
        }
    }
}
</script>


<!-- STYLE -->
<style lang="scss" scoped>
@import "../styles/variables.scss";

// MIXINS
@mixin flex {
    display: flex;
    justify-content: space-between
}

@mixin highlight {
    border-bottom: 4px solid $clr-primary;
}


// BLOCKS
.header-content {
    @include flex();
    align-items: center;
}


.main-logo {
    max-width: 65px;
}


.nav-bar {
    flex-basis: 70%;
    max-width: 700px;

    .nav-list {
        @include flex();
    }
}


.nav-item {
    text-transform: uppercase;
    padding: 2.5rem 0;
    cursor: pointer;

    // Transition
    transition: color 200ms ease;

    &.active {
        @include highlight();
        color: $clr-primary;
    }

    @media (hover: hover) {
        &:hover {
            @include highlight();
            color: lighten($clr-primary, 25%);
        }
    }
    
}
</style>