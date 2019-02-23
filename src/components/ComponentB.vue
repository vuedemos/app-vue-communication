<template>
    <div class="component-b">
        <h3>组件B中的props: {{ age }}</h3>
        <p>组件B中的$attrs: {{ $attrs }}</p>
        <p>组件B中的$listeners: {{ $listeners }}</p>

        <hr />
        <ComponentC v-bind="$attrs" v-on="$listeners" />
    </div>
</template>

<script>
import ComponentC from './ComponentC'

export default {
    name: 'ComponentB',
    props: {
        age: {
            type: Number,
            default: 30
        }
    },
    inheritAttrs: false,
    components: {
        ComponentC
    },
    mounted () {
        this.$emit('test1')
        console.log('ComponentB',this.$attrs, this.$listeners)
    }
}
</script>

<style scoped>
    .mask-overlay {
        position: fixed;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0, 0, 0, .3);
    }
</style>
