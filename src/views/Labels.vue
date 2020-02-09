<template>
  <Layout>
    <ul class="tagsList">
      <li>
          <span>网购</span>
          <Icon name="right"/>
      </li>
      <li>
          <span>吃饭</span>
          <Icon name="right"/>
      </li>
      <li>
          <span>充值</span>
          <Icon name="right"/>
      </li>
      <li>
          <span>生活缴费</span>
          <Icon name="right"/>
      </li>
    </ul>
    <div class="new-tag-wrapper">
      <button class="new-tag">新增标签</button>
    </div>
  </Layout>
</template>

<script lang="ts">
  import Vue from 'vue';

  export default class Labels extends Vue {}
</script>

<style lang="scss" scoped>
.tagsList{
    background: white;
    font-size: 16px;
    padding-left: 16px;
    li{
        height: 44px;
        border-bottom: 1px solid #e5e5e5;
        display: flex;
        align-items: center;
        justify-content: space-between;
        svg{
            width: 24px;
            height: 24px;
            margin-right: 16px;
            background: #eee;
            border-radius: 50%;
        }
    }
    }

.new-tag {
    font-size: 20px;
    height: 42px;
    background: #999;
    color: #eee;
    padding: 0 16px;
    border-radius: 4px;
    &-wrapper{
        text-align: center;
        margin-top: 48px;
    }
}
</style>