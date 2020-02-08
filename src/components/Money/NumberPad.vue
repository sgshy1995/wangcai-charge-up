<template>
  <div class="number-pad">
    <div class="output">{{output}}</div>
    <div class="keys">
      <button @click="changeOutput">1</button>
      <button @click="changeOutput">2</button>
      <button @click="changeOutput">3</button>
      <button @click="deleteOutput">删除</button>
      <button @click="changeOutput">4</button>
      <button @click="changeOutput">5</button>
      <button @click="changeOutput">6</button>
      <button @click="clearOutput">清除</button>
      <button @click="changeOutput">7</button>
      <button @click="changeOutput">8</button>
      <button @click="changeOutput">9</button>
      <button @click="commitOutput" class="ok">确认</button>
      <button @click="changeOutput" class="zero">0</button>
      <button @click="changeOutput">.</button>
    </div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue';
  import {Component} from 'vue-property-decorator';

  @Component
  export default class NumberPad extends Vue {
    output: string = '0';

    changeOutput(event: MouseEvent) {
      const input = (event.target as HTMLButtonElement).textContent as string;
      if (this.output.length === 16) {
        return;
      }
      if (this.output === '0') {
        if ('0123456789'.indexOf(input) >= 0) {
          this.output = input;
        } else {
          this.output += input;
        }
        return;
      }
      if (this.output.indexOf('.') >= 0 && input === '.') {
        return;
      }
      this.output += input;
    }

    clearOutput() {
      this.output = '0';
    }

    deleteOutput() {
      if (this.output.length === 1) {
        this.output = '0';
      } else {
        this.output = this.output.slice(0, -1);
      }
    }

    commitOutput(){
      return;
    }
  }
</script>

<style scoped lang="scss">
  @import "~@/assets/styles/global.scss";

  .number-pad {
    .output {
      font-size: 36px;
      font-family: Consolas, monospace;
      padding: 9px 16px;
      text-align: right;
      box-shadow: $box-shadow-inner;
    }

    .keys {
      @extend %clear-fix;

      button {
        float: left;
        width: 25%;
        height: 64px;


        &.ok {
          height: 128px;
          float: right;
        }

        &.zero {
          width: 50%;
        }

        $bg: #F4F4F4;

        &:nth-child(1) {
          background: $bg;
        }

        &:nth-child(2), &:nth-child(5) {
          background: darken($bg, 5%);
        }

        &:nth-child(3), &:nth-child(6), &:nth-child(9) {
          background: darken($bg, 10%);
        }

        &:nth-child(4), &:nth-child(7), &:nth-child(10) {
          background: darken($bg, 15%);
        }

        &:nth-child(8), &:nth-child(11), &:nth-child(13) {
          background: darken($bg, 20%);
        }

        &:nth-child(14) {
          background: darken($bg, 25%);
        }

        &:nth-child(12) {
          background: darken($bg, 30%);
        }

        &:active{
          box-shadow: inset 0 0 5px 0 fade_out(black,0.5);
        }

      }
    }
  }
</style>