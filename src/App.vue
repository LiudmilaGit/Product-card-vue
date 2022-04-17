<template>
  <nav class="navigation">
    <router-link :to="{ name: 'home' }">Home</router-link>
    <router-link :to="{ name: 'cart' }">Cart</router-link>
  </nav>
  <router-view />
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
html,
body {
  margin: 0;
  padding: 0;
}

body {
  border-color: aliceblue;
}

.navigation {
  padding: 10px;
  width: 100%;
  height: 30px;
  background-color: #fff;
  line-height: 30px;
  font-size: 24px;

  a {
    font-weight: bold;
    color: #676869;
    text-decoration: none;
    margin: 0 5px 0 5px;

    &.router-link-exact-active {
      color: #1a152e;
      transition: all 0.5s ease-in;
    }
  }
}
</style>
