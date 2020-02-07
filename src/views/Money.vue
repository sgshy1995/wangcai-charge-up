<template>
    <Layout>
        <div class="tags">
            <ul class="current">
                <li>衣</li>
                <li>食</li>
                <li>住</li>
                <li>行</li>
            </ul>
            <div class="new">
                <button>新增标签</button>
            </div>
        </div>
        <div>
            <label class="notes">
                <span class="name">备注</span>
                <input type="text">
            </label>
        </div>
        <div>
            <ul class="types">
                <li>支出</li>
                <li>收入</li>
            </ul>
        </div>
        <div class="number-pad">
            <div class="output">100</div>
            <div class="keys">
                <button>1</button>
                <button>2</button>
                <button>3</button>
                <button>delete</button>
                <button>4</button>
                <button>5</button>
                <button>6</button>
                <button>clear</button>
                <button>7</button>
                <button>8</button>
                <button>9</button>
                <button>ok</button>
                <button>0</button>
                <button>.</button>
            </div>
        </div>
    </Layout>
</template>

<script lang="ts">
    export default {}
</script>

<style lang="scss" scoped>
.nav-wrapper{
  display: flex;
  flex-direction: column;
  height: 100vh;
  .content{
    flex-grow: 1;
  }
}
</style>