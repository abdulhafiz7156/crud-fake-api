<template>
  <router-view/>
</template>

<style lang="scss">
#app {
  font-family: "Inter";
  color: #000;
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
