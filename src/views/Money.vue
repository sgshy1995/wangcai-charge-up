<template>
  <Layout prefix-class="money">
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
    <div>
      <ul class="types">
        <li class="selected">支出</li>
        <li>收入</li>
      </ul>
    </div>
    <div>
      <label class="notes">
        <span class="name">备注</span>
        <input type="text" placeholder="在这里输入备注">
      </label>
    </div>
    <div class="tags">
      <div class="new">
        <button>新增标签</button>
      </div>
      <ul class="current">
        <li>衣</li>
        <li>食</li>
        <li>住</li>
        <li>行</li>
      </ul>
    </div>
  </Layout>
</template>

<script lang="ts">
  export default {}
</script>

<style lang="scss">
  .money-content{
    display: flex;
    flex-direction: column-reverse;
  }
</style>

<style lang="scss" scoped>
  @import "~@/assets/styles/global.scss";

  .tags {
    padding: 16px;
    font-size: 14px;
    display: flex;
    flex-direction: column-reverse;
    flex-grow: 1;

    .current {
      display: flex;
      flex-direction: row;

      li {
        $h: 1.5em;
        height: $h;
        line-height: $h;
        background: #aaaaaa;
        padding: 0 1em;
        margin-right: 1em;
        margin-top: .2em;
        border-radius: $h/2;
      }
    }

    .new {
      padding-top: 16px;

      button {
        background: transparent;
        border: none;
        color: #999;
        border-bottom: 1px solid #777;
        cursor: pointer;
        padding: 0 .3em;
      }
    }
  }

  .notes {
    padding-left: 16px;
    background: #f5f5f5;
    font-size: 14px;
    display: flex;
    align-items: center;

    .name {
      padding-right: 16px;
    }

    input {
      padding: 16px 16px 16px 0;
      flex-grow: 1;
      background: transparent;
      border: none;
    }
  }

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