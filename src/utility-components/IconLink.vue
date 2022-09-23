<template>
<a :href="link">
    <img :src="logoPath" :alt="description">
</a>
</template>

<script>
export default {
    name: "IconLink",

    props: {
        logoPath: String,
        link: String,
        description: String,
    }
}
</script>


<style lang="scss" scoped>

</style>