<template>
<header>
    <h1 class="visually-hidden">DC Comics</h1>
    <div class="header-content container">
        <div>
            <img class="main-logo img-fluid" src="../assets/img/dc-logo.png" alt="DC Logo">
        </div>
        
        <nav class="nav-bar">
            <ul class="nav-list fs-5">
                <li v-for="navItem in navList" :key="navItem">
                    <a class="nav-item" href="#">{{ navItem }}</a>
                </li>
            </ul>
        </nav>
    </div>
</header>
</template>

<script>
export default {
    name: "PageHeader",

    data() {
        return {
            navList: ["Characters", "Comics", "Movies", "TV", "Games", "Collectibles", "Videos", "Fans", "News", "Shop"],
        }
    }
}
</script>

<style lang="scss" scoped>
@mixin flex {
    display: flex;
    justify-content: space-between
}

.header-content {
    @include flex();
    align-items: center;
}

.main-logo {
    max-width: 90px;
}

.nav-bar {
    flex-basis: 70%;
    max-width: 700px;
}

.nav-list {
        @include flex();
}

.nav-item {
    text-transform: uppercase;
}
</style>