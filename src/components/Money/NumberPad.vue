<template>
  <div class="number-pad">
    <div class="output">100</div>
    <div class="keys">
      <button>1</button>
      <button>2</button>
      <button>3</button>
      <button>删除</button>
      <button>4</button>
      <button>5</button>
      <button>6</button>
      <button>清除</button>
      <button>7</button>
      <button>8</button>
      <button>9</button>
      <button class="ok">确认</button>
      <button class="zero">0</button>
      <button>.</button>
    </div>
  </div>
</template>

<script lang="ts">
  export default {
    name: "NumberPad"
  }
</script>

<style scoped lang="scss">
  @import "~@/assets/styles/global.scss";
  .number-pad {
    .output {
      font-size: 36px;
      font-family: Consolas, monospace;
      padding: 9px 16px;
      text-align: right;
      box-shadow: $box-shadow-inner;
    }

    .keys {
      @extend %clear-fix;

      button {
        float: left;
        width: 25%;
        height: 64px;

        &.ok {
          height: 128px;
          float: right;
        }

        &.zero {
          width: 50%;
        }

        $bg: #F4F4F4;

        &:nth-child(1) {
          background: $bg;
        }

        &:nth-child(2), &:nth-child(5) {
          background: darken($bg, 5%);
        }

        &:nth-child(3), &:nth-child(6), &:nth-child(9) {
          background: darken($bg, 10%);
        }

        &:nth-child(4), &:nth-child(7), &:nth-child(10) {
          background: darken($bg, 15%);
        }

        &:nth-child(8), &:nth-child(11), &:nth-child(13) {
          background: darken($bg, 20%);
        }

        &:nth-child(14) {
          background: darken($bg, 25%);
        }

        &:nth-child(12) {
          background: darken($bg, 30%);
        }
      }
    }
  }
</style>