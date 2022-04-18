<template>
<div class="wrapper">
  <div class="container">
  <nav class="navigation">
    <router-link :to="{ name: 'home' }">Home</router-link>
    <router-link :to="{ name: 'cart' }">Cart</router-link>
  </nav>
  <router-view />
  </div>
  </div>
</template>
<script>
import { mapMutations } from 'vuex'
export default {
mounted() {
  this.updateLocalStorage()
},


  methods: {
    ...mapMutations(['updateCartFromLocalStorage']),

    updateLocalStorage() {
      return this.updateCartFromLocalStorage()
    }
  },

}
</script>

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
  box-sizing: border-box;
}
.wrapper{
  display: flex;
  flex-direction: column;
  min-height: 100%;
  overflow: hidden;
}
.container{
  max-width: 1730px;
  margin: 0 auto;
  padding: 0 15px;

}

.navigation {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px;
  width: 100%;
  height: 50px;
  background-color: #fff;
  line-height: 30px;
  font-size: 24px;

  a {
    font-weight: bold;
    color: #676869;
    text-decoration: none;
    margin: 0 10px 0 10px;

    &.router-link-exact-active {
      color: #1a152e;
      transition: all 0.5s ease-in;
    }
  }
  .text-center{
    text-align: center;
  }
}
</style>
