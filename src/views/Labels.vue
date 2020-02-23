<template>
  <Layout>
    <div class="tagsList">
      <router-link class="tag" :to="`/labels/edit/${tag.id}`" v-for="tag in tags" :key="tag.id">
        <span>{{tag.name}}</span>
        <Icon name="right"/>
      </router-link>
    </div>
    <div class="new-tag-wrapper">
      <Button @click.native="createTag">新增标签</Button>
    </div>
  </Layout>
</template>

<script lang="ts">
  import Vue from 'vue';
  import {Component} from 'vue-property-decorator';
  import tagListModel from '@/models/tagListModel';
  import Button from '@/components/Button.vue';

  tagListModel.fetch();
  @Component({
    components: {Button}
  })
  export default class Labels extends Vue {
    tags = tagListModel.data;

    createTag() {
      const name = window.prompt('请输入标签名：');
      if (name) {
        const message = tagListModel.create(name);
        if (message === 'duplicated') {
          window.alert('标签已存在！');
        }
      } else {
        window.alert('标签不可为空！');
      }
    }
  }
</script>

<style lang="scss" scoped>
  .tagsList {
    background: white;
    font-size: 16px;
    padding-left: 16px;

    .tag {
      height: 44px;
      border-bottom: 1px solid #e5e5e5;
      display: flex;
      align-items: center;
      justify-content: space-between;

      svg {
        width: 24px;
        height: 24px;
        margin-right: 16px;
        background: #eee;
        border-radius: 50%;
      }
    }
  }


  .new-tag-wrapper {
    text-align: center;
    margin-top: 48px;
  }

</style>