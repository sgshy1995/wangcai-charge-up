<template>
    <div class="nav-wrapper">
        <div class="content">Money</div>
        <Nav></Nav>
    </div>
</template>

<script lang="ts">
    export default {}
</script>

<style lang="scss" scoped>
.nav-wrapper{
  display: flex;
  flex-direction: column;
  height: 100vh;
    border: 1px solid gold;
  .content{
    flex-grow: 1;
      border: 1px solid brown;
  }
}
</style>