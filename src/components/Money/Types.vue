<template>
  <div>
    <ul class="types">
      <li class="selected">支出</li>
      <li>收入</li>
    </ul>
  </div>

</template>

<script lang="ts">
  export default {
    name: "Types"
  }
</script>

<style scoped lang="scss">
  .types {
    background: #c4c4c4;
    display: flex;
    flex-direction: row;
    font-size: 24px;

    li {
      width: 50%;
      padding: .5em 0;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      position: relative;

      &.selected {
        &::after {
          content: '';
          display: block;
          width: 100%;
          height: 2px;
          background: #333333;
          position: absolute;
          bottom: 0;
          left: 0;
        }
      }
    }
  }
</style>