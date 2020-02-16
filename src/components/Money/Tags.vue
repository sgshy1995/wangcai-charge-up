<template>
  <div class="tags">
    <div class="new">
      <button @click="addTags">新增标签</button>
    </div>
    <ul class="current">
      <li :class="{'selected':selectedTags.indexOf(tag)>=0}" v-for="tag in dataResource" :key="tag.id"
          @click="toggle(tag)">
        {{tag}}
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue';
  import {Component, Prop} from 'vue-property-decorator';

  @Component
  export default class Tags extends Vue {
    @Prop(Array) readonly dataResource: string[] | undefined;
    @Prop(Array) readonly value!:string[];
    selectedTags: string[] = this.value;

    toggle(tag: string) {
      const index = this.selectedTags.indexOf(tag);
      if (index >= 0) {
        this.selectedTags.splice(index, 1);
      } else {
        this.selectedTags.push(tag);
      }
      this.$emit('update:value',this.selectedTags)
    }

    addTags() {
      const name = window.prompt('请输入标签名：');
      if (name === '') {
        window.alert('标签名不可为空！');
      } else if (this.dataResource) {
        if (this.dataResource.indexOf(name!) >= 0) {
          window.alert('标签名已存在！');
        } else {
          this.$emit('update:dataResource', [...this.dataResource, name]);
        }
      }
    }
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
      flex-wrap: wrap;

      li {
        $h: 1.5em;
        $bg: #d9d9d9;
        height: $h;
        line-height: $h;
        background: $bg;
        padding: 0 1em;
        margin-right: 1em;
        margin-top: .2em;
        border-radius: $h/2;
        cursor: pointer;

        &.selected {
          background: darken($bg, 30%);
          color: #ffffff;
        }
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