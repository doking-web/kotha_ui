<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view/>
  </div>
</template>

<style lang="scss">
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
:root{
    //#e8e8e8 -bfbfbf-96939b-564256-fc814a
    --color-acsent: #fc814a;
    --color-primary: #564256;
    --color-light-gray: #e8e8e8;
    --color-dark-gray: #bfbfbf;
  }
  .link{
    text-decoration: none;
    color: #000;
  }

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--color-primary);
}
</style>
