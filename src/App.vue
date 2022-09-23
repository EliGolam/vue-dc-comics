<template>
  <div id="app">
    <!-- HEADER -->
    <PageHeader :navLinks="headerLinks" />
    <!-- MAIN -->
    <PageMain />
    <!-- FOOTER -->
    <PageFooter :navLinks="footerLinks" :socials="socialLinks"/>
  </div>
</template>

<script>
/* DATA */
import { DATA } from '@/data/data.js';

/* COMPONENTS */
import PageHeader from './components/PageHeader.vue';
import PageMain from './components/PageMain.vue';
import PageFooter from './components/PageFooter.vue';



export default {
  name: 'App',
  components: {
    PageHeader,
    PageMain,
    PageFooter,
  },

  data() {
    return {
      headerLinks: DATA.headerLinks,
      footerLinks: DATA.footerLinks,
      socialLinks: DATA.socialLinks,
    }
  }
}
</script>

<style lang="scss">
@import "@/styles/style.scss"

</style>
