<template>
    <nav>
        <router-link to="/Money" class="item" active-class="selected">
            <Icon name="money"></Icon>
            记 账
        </router-link>
        <router-link to="/labels" class="item" active-class="selected">
            <Icon name="labels"></Icon>
            标 签
        </router-link>
        <router-link to="/statistics" class="item" active-class="selected">
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
    @import "~@/assets/styles/global.scss";
    nav{
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        box-shadow: $box-shadow-outer;
        font-size: 14px;
        color: $color-nav;
        .item{
            width: 33.3333333%;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            padding-top: .8em;
            padding-bottom: .5em;
            border: 1px solid $color-border-nav;
            border-bottom: none;
            border-top: none;
            background: $background-nav;
            &.selected{
                color: $color-nav-focus;
                background: $background-nav-focus;
            }
            svg{
                margin-bottom: .4em;
            }
        }
    }
</style>