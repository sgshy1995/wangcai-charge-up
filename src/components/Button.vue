<template>
  <button class="new-tag">
    <slot></slot>
  </button>
</template>

<script lang="ts">
  import Vue from 'vue';
  import {Component} from 'vue-property-decorator';

  @Component
  export default class Button extends Vue {

  }
</script>

<style scoped lang="scss">
  .new-tag {
    font-size: 20px;
    height: 42px;
    background: transparent;
    border-radius: 4px;
    color: #333;
    padding: 0 16px;
    border: 1px solid black;

    &-wrapper {
      text-align: center;
      margin-top: 48px;
    }
  }
</style>