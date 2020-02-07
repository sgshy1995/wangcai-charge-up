<template>
    <nav>
        <router-link to="/Money" class="item">
            <Icon name="money"></Icon>
            记 账
        </router-link>
        <router-link to="/labels" class="item">
            <Icon name="labels"></Icon>
            标 签
        </router-link>
        <router-link to="/statistics" class="item">
            <Icon name="statistics"></Icon>
            统 计
        </router-link>
    </nav>
</template>

<script lang="ts">
    let importAll = (requireContext: __WebpackModuleApi.RequireContext) => requireContext.keys().forEach(requireContext);
    try {
    importAll(require.context('../assets/icons', true, /\.svg$/));
    }catch (e) {
        console.log(e);
    }

    export default {}
</script>

<style lang="scss" scoped>
    nav{
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        box-shadow: 0 0 3px rgba(0,0,0,0.25);
        font-size: 14px;
        .item{
            width: 33.3333333%;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            padding-top: .3em;
        }
    }
</style>