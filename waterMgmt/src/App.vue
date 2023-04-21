<template>
  <div id="app">
    <header>
      <span>Neptune</span>
    </header>
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #35495e2d;
}

main {
  text-align: center;
  margin-top: 0px;
}

header {
  margin: 0px;
  height: 0px;
  padding: 0 16px 0 24px;
  background-color: #ffffff;
  color: #ffffff;
}

header span {
  display: block;
  position: relative;
  font-size: 30px;
  line-height: 1;
  letter-spacing: .02em;
  font-weight: 400;
  box-sizing: border-box;
  padding-top: 16px;
  z-index: 1;
  color: #00000050;
}

footer {
  margin: 0px;
}
</style>
