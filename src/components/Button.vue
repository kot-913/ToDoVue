<template>
    <button @click="onClick()" v-bind:style='{ background: color, width: width}'>{{text}}</button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: String,
        color: String,
        width: String,
    },
    methods: {
        onClick(){
            this.$emit('btn-click');
        }
    }
}
</script>

<style scoped>

</style>