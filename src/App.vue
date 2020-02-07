<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script lang="ts">

</script>

<style lang="scss">
  @import "~@/assets/styles/reset.scss";
  @import "~@/assets/styles/global.scss";
  body{
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    font-family: $font-hei;
    color: $color;
    line-height: $line-height;
  }
</style>
