<template>
  <div>
    <label class="notes">
      <span class="name">{{fieldName}}</span>
      <input type="text" :placeholder="placeholder" v-model="content">
    </label>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue';
  import {Component, Prop, Watch} from 'vue-property-decorator';

  @Component
  export default class Notes extends Vue {
    @Prop({default:''}) readonly value!:string;
    @Prop({required:true}) fieldName!:string;
    @Prop() placeholder?:string;
    content:string = this.value;

    @Watch('content')
    onValueChanged(value: string) {
      this.$emit('update:value', value);
    }
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