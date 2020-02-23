<template>
  <Layout>
    <div class="navBar">
      <Icon class="leftIcon" name="left"></Icon>
      <span class="title">编辑标签</span>
    </div>
    <div class="notesWrapper">
      <Notes field-name="标签名" placeholder="请输入标签名"/>
    </div>
    <div class="buttonWrapper">
      <Button>删除标签</Button>
    </div>
  </Layout>
</template>

<script lang="ts">
  import Vue from 'vue';
  import {Component} from 'vue-property-decorator';
  import tagListModel from '@/models/tagListModel';
  import Notes from '@/components/Money/Notes.vue';
  import Button from '@/components/Button.vue';

  @Component({
    components: {Button, Notes}
  })
  export default class EditLabel extends Vue {
    created() {
      tagListModel.fetch();
      const id = this.$route.params.id;
      const tags = tagListModel.data;
      const tag = tags.filter(t => t.id === id)[0];
      if (tag) {
        console.log(tag);
      } else {
        this.$router.replace('/404');
      }
    }
  }
</script>

<style scoped lang="scss">
  .navBar {
    text-align: center;
    position: relative;
    font-size: 16px;
    height: 48px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: white;

    .leftIcon {
      position: absolute;
      left: 16px;
      top: 50%;
      transform: translateY(-50%);
      background: #eeeeee;
      border-radius: 50%;
    }
  }

  .notesWrapper {
    background: white;
    margin-top: 8px;
  }
  .buttonWrapper{
    text-align: center;
    padding-top: 44px;
    cursor: pointer;
  }
</style>