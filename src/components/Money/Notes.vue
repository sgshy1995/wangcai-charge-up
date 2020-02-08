<template>
  <div>
    <label class="notes">
      <span class="name">备注</span>
      <input type="text" placeholder="在这里输入备注">
    </label>
  </div>
</template>

<script lang="ts">
  export default {
    name: "Notes"
  }
</script>

<style scoped lang="scss">
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
</style>