<template>
  <div class="app-class">
    <router-view />
  </div>
</template>

<style lang="scss">
.app-class {
  width: 100%;
  height: 100vh;
  background-color: #000;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  .content_wrap {
    color: #fff;
    padding: 0;
  }
}

nav {
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
