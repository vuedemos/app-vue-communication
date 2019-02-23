<template>
    <div class="modal-header">
        <h5 class="modal-title">{{ modalTitle }}</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close" @click="close">
          <span aria-hidden="true">&times;</span>
        </button>
    </div>
</template>

<script>
export default {
    name: 'ModalHeader',
    props: {
        modalTitle: {
            type: String,
            default: 'Modal Title'
        }
    },
    inheritAttrs: false,
    methods: {
        close () {
            this.$emit('on-close')
        }
    },
    mounted () {
        console.log('ModalHeader',this.$attrs, this.$listeners)
    }
}
</script>

<style scoped>
.modal-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem;
    border-bottom: 1px solid #e9ecef;
    border-radius: .3rem .3rem 0 0;
}

.modal-title {
    margin: 0;
}

.close {
    font-size: 1.5rem;
    font-weight: 700;
    line-height: 1;
    color: #000;
    text-shadow: 0 1px 0 #fff;
    opacity: .5;
    background-color: transparent;
    border: 0;
    -webkit-appearance: none;
    padding: 1rem;
    margin: -1rem -1rem -1rem auto;
}

.close:not(:disabled):not(.disabled) {
    cursor: pointer;
}
</style>
