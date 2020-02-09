<template>
  <Layout prefix-class="money">
    <NumberPad :value.sync="record.amount" @submit="saveRecord"></NumberPad>
    <Types :value.sync="record.type"></Types>
    <Notes :value.sync="record.notes"></Notes>
    <Tags :data-resource.sync="tags" :value.sync="record.tags"></Tags>
  </Layout>
</template>

<script lang="ts">
  import Vue from 'vue';
  import {Component, Watch} from 'vue-property-decorator';
  import NumberPad from "@/components/Money/NumberPad.vue";
  import Types from "@/components/Money/Types.vue";
  import Notes from "@/components/Money/Notes.vue";
  import Tags from "@/components/Money/Tags.vue";

  {
    // 数据库相关 可忽略 只为演示
    const version = window.localStorage.getItem('moneyVersion');
    const recordList: Record[] = JSON.parse(window.localStorage.getItem('recordList') || '[]');
    if (version === '1.0.0') {
      // 数据库升级  （数据迁移）
      recordList.forEach(record => {
        record.createTime = new Date(2020, 0, 1);
      });
      // 保存数据
      window.localStorage.setItem('recordList', JSON.stringify(recordList));
    }
    // 升级版本号
    window.localStorage.setItem('moneyVersion', '1.0.1');
  }

  type Record = {
    tags: string[]
    notes: string
    type: string
    amount: number
    createTime?: Date
  }

  @Component({
    components: {Tags, Notes, Types, NumberPad}
  })
  export default class Money extends Vue {

    tags = ['网购', '吃饭', '充值', '生活缴费'];
    record: Record = {
      tags: [],
      notes: '',
      type: '-',
      amount: 0
    };
    recordList: Record[] = JSON.parse(window.localStorage.getItem('recordList') || '[]');

    saveRecord() {
      const deepCopyRecord: Record = JSON.parse(JSON.stringify(this.record));
      deepCopyRecord.createTime = new Date();
      this.recordList.push(deepCopyRecord);
    }

    @Watch('recordList')
    onRecordListChanged() {
      window.localStorage.setItem('recordList', JSON.stringify(this.recordList));
    }
  }
</script>

<style lang="scss">
  .money-content {
    display: flex;
    flex-direction: column-reverse;
  }
</style>
