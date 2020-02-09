<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script lang="ts">
export default {}
</script>

<style lang="scss">
  @import "~@/assets/styles/reset.scss";
  @import "~@/assets/styles/global.scss";
  body{
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-family: $font-hei;
    color: $color;
    font-size: $font-size;
    line-height: $line-height;
    background: #F6F6F6;
  }
</style>
