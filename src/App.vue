<template>
  <div id="app">
    <nav-principal id="nav"></nav-principal>
    <router-view />
  </div>
</template>

<script>
import navPrincipal from "@/components/Nav.vue";

export default {
  components: {
    "nav-principal": navPrincipal,
  }
}
</script>


<style lang="scss">
@import "~@/assets/scss/vendors/bootstrap-vue/index";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #ffffff;
    }
  }
}
</style>
