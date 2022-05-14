<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/cart">Cart</router-link>
    </nav>
    <router-view/>
  </div>
</template>

<script>
export default {
  mounted() {
    this.$store.commit('updateCartFromLocalStorage')
  }
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

nav {
  padding: 10px;
  width: 100%;
  height: 30px;
  background-color: #fff;
  line-height: 30px;

  a {
    font-weight: bold;
    color: darkgray;
    text-decoration: none;
    margin: 0 5px;
    font-size: 1.25rem;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

html, body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
  box-sizing: border-box;
}

body {
  background-color: rgb(245, 245, 245);
}
</style>
