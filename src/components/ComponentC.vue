<template>
    <div class="component-c">
        <h3>组件C中设置的props: {{ name }}</h3>
        <p>组件C中的$attrs: {{ $attrs }}</p>
        <p>组件C中的$listeners: {{ $listeners }}</p>
    </div>
</template>

<script>
export default {
    name: 'ComponentC',
    props: {
        name: {
            type: String,
            default: '大漠'
        }
    },
    inheritAttrs: false,
    mounted () {
        this.$emit('test2')
        console.log('ComponentC',this.$attrs, this.$listeners)
    }
}
</script>

<style scoped>
</style>
