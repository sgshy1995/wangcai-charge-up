<template>
    <svg class="icon" aria-hidden="true">
        <use :xlink:href="`#${name}`"></use>
    </svg>
</template>

<script lang="ts">
    export default {
        name: "Icon",
        props:{
            name:{
                type:[String,Number],
                required:true
            }
        }
    }
</script>

<style scoped lang="scss">
    .icon {
        width: 1.5em;
        height: 1.5em;
        vertical-align: -0.15em;
        fill: currentColor;
        overflow: hidden;
    }
</style>