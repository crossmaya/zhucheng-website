<template>
  <div id="app">
    <keep-alive>
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>

export default {
  name: 'App',
}
</script>

<style lang="less">
#app {
  font-family: Microsoft YaHei;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*min-width: 1280px;*/
  background: #F7FAFC;
  /*text-align: center;*/
  /*color: #2c3e50;*/
}
</style>
