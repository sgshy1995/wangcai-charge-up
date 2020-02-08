<template>
    <div class="layout-wrapper" :class="prefixClass && `${prefixClass}-wrapper`">
        <div class="content" :class="prefixClass && `${prefixClass}-content`">
            <slot></slot>
        </div>
        <Nav></Nav>
    </div>
</template>

<script lang="ts">
    export default {
        name: "Layout",
        props:['prefixClass']
    }
</script>

<style scoped lang="scss">
    .layout-wrapper {
        display: flex;
        flex-direction: column;
        height: 100vh;
        .content {
            flex-grow: 1;
        }
    }
</style>