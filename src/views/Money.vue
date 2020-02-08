<template>
  <Layout prefix-class="money">
    <NumberPad></NumberPad>
    <Types></Types>
    <Notes></Notes>
    <Tags :data-resource.sync="tags"></Tags>
  </Layout>
</template>

<script>
  import NumberPad from "@/components/Money/NumberPad.vue";
  import Types from "@/components/Money/Types.vue";
  import Notes from "@/components/Money/Notes.vue";
  import Tags from "@/components/Money/Tags.vue";
  export default {
    name:"Money",
    data(){
      return{
        tags:['网购','吃饭','充值','生活缴费']
      }
    },
    components: {Tags, Notes, Types, NumberPad}
  }
</script>

<style lang="scss">
  .money-content{
    display: flex;
    flex-direction: column-reverse;
  }
</style>
