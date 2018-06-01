<template>
  <div id="app">

    <app-header></app-header>

    <app-page v-for="page in pages" :key="page.id" :page="page"></app-page>

    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  </div>
</template>

<script>
  import {
    mapState,
    mapGetters,
    mapMutations,
    mapActions
  } from 'vuex';
  import store from '../store';

  export default {

    name: "app",
    store,
    computed: {
      ...mapState(['pages']),
    },
    components: {
      AppHeader: require('../components/AppHeader').default,
      AppPage: require('../components/AppPage').default
    }
  };
</script>

<style lang="less">
  @import (once) "../styles/style";
</style>