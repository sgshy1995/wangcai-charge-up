<template>
    <div class="nav">
        <router-link to="/Money">
            <Icon name="money"></Icon>
            记 账
        </router-link>
        |
        <router-link to="/labels">
            <Icon name="labels"></Icon>
            标 签
        </router-link>
        |
        <router-link to="/statistics">
            <Icon name="statistics"></Icon>
            统 计
        </router-link>
    </div>
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
</style>