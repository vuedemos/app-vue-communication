<template>
    <div class="modal-backdrop" v-if="show" @click="close">
    </div>
</template>

<script>

export default {
    name: 'MaskBackdrop',
    props: {
        show: {
            type: Boolean,
            default: false
        }
    },
    inheritAttrs: false,
    mounted () {
        console.log('MaskBackdrop',this.$attrs, this.$listeners)
    },
    methods: {
        close () {
            this.$emit('on-close')
        }
    }
}
</script>

<style scoped>
.modal-backdrop {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 1040;
    background-color: rgba(0,0,0,.5);
}
</style>
