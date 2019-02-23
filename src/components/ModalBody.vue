<template>
    <div class="modal-body">
        <slot>{{ modalContent }}</slot>
    </div>
</template>

<script>
export default {
    name: 'ModalBody',
    props: {
        modalContent: {
            type: String,
            default: 'Modal body text goes here.'
        }
    },
    inheritAttrs: false,
    mounted () {
        console.log('ModalBody',this.$attrs, this.$listeners)
    }
}
</script>

<style scoped>
.modal-body {
    position: relative;
    flex: 1 1 auto;
    padding: 1rem;
}
</style>
