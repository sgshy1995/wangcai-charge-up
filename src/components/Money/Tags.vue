<template>
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
</template>

<script lang="ts">
  export default {
    name: "Tags"
  }
</script>

<style scoped lang="scss">
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
</style>