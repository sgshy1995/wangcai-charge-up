<template>
  <Layout prefix-class="money">
    <NumberPad :value.sync="record.amount"></NumberPad>
    <Types :value.sync="record.type"></Types>
    <Notes :value.sync="record.notes"></Notes>
    <Tags :data-resource.sync="tags" :value.sync="record.tags"></Tags>
  </Layout>
</template>

<script lang="ts">
  import Vue from 'vue';
  import {Component} from 'vue-property-decorator';
  import NumberPad from "@/components/Money/NumberPad.vue";
  import Types from "@/components/Money/Types.vue";
  import Notes from "@/components/Money/Notes.vue";
  import Tags from "@/components/Money/Tags.vue";

  type Record = {
    tags: string[]
    notes: string
    type: string
    amount: number
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
  }
</script>

<style lang="scss">
  .money-content {
    display: flex;
    flex-direction: column-reverse;
  }
</style>
