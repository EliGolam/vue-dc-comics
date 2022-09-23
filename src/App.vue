<template>
  <div id="app">
    <!-- HEADER -->
    <PageHeader />
    <!-- MAIN -->
    <PageMain />
    <!-- FOOTER -->
    <PageFooter />
  </div>
</template>

<script>
import PageHeader from './components/PageHeader.vue';
import PageMain from './components/PageMain.vue';
import PageFooter from './components/PageFooter.vue';

export default {
  name: 'App',
  components: {
    PageHeader,
    PageMain,
    PageFooter
}
}
</script>

<style lang="scss">
@import "./styles/variables.scss";
@import "./styles/personal-reset.scss";
@import "./styles/utilties.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-size: $fs-default;
  font-weight: $fw-default;

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
</style>
