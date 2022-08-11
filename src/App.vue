<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view />
</template>

<style lang="scss">
@import "~primevue/resources/themes/saga-blue/theme.css"; //theme
// @import "~primevue/resources/themes/tailwind-light/theme.css";
@import "~primevue/resources/primevue.min.css";
@import "~primeicons/primeicons.css";
@import "/node_modules/primeflex/primeflex.scss";

#app {
  font-family: "Lobster", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
