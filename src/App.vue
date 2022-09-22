<template>
  <div id="app">
    <!-- HEADER -->
    <PageHeader />
    <!-- MAIN -->
    <!-- FOOTER -->
  </div>
</template>

<script>
import PageHeader from './components/PageHeader.vue';

export default {
  name: 'App',
  components: {
    PageHeader
}
}
</script>

<style lang="scss">
@import "./styles/variables.scss";
@import "./styles/personal-reset.scss";
@import "./styles/utilties.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-size: $fs-4;

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
</style>
