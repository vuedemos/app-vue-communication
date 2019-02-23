<template>
    <div class="component-b">
        <div class="mask" v-if="show">
            <div class="mask-overlay"></div>
            <ComponentC v-bind="$attrs" v-on="$listeners" />
        </div>
    </div>
</template>

<script>
import ComponentC from './ComponentC'

export default {
    name: 'ComponentB',
    props: {
        show: {
            type: Boolean,
            default: false
        }
    },
    inheritAttrs: false,
    components: {
        ComponentC
    },
    mounted () {
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
