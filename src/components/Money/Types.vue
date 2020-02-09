<template>
  <div>
    <ul class="types">
      <li :class="selectedType==='-' && 'selected'" @click="changeType('-')">支出</li>
      <li :class="selectedType==='+' && 'selected'" @click="changeType('+')">收入</li>
    </ul>
  </div>

</template>

<script lang="ts">
  import Vue from 'vue';
  import {Component, Prop, Watch} from "vue-property-decorator";

  @Component
  export default class Types extends Vue {
    selectedType = '-'; // - 为支出 + 为收入
    @Prop(Number) myNumber: number | undefined;

    changeType(type: string) {
      if (type === '-' || type === '+') {
        this.selectedType = type;
      } else {
        throw new Error('Unknown Type');
      }
    }

    @Watch('selectedType')
    onTypeChanged(value: string) {
      this.$emit('update:value', value);
    }
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