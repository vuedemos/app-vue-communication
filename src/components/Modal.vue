<template>
    <div class="modal" tabindex="-1" role="dialog" v-if="show">
        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <ModalHeader v-bind="$attrs" v-on="$listeners" />
                <ModalBody v-bind="$attrs" v-on="$listeners" />
                <ModalFooter v-bind="$attrs" v-on="$listeners" />
            </div>
        </div>
    </div>
</template>

<script>
import ModalHeader from './ModalHeader'
import ModalBody from './ModalBody'
import ModalFooter from './ModalFooter'

export default {
    name: 'Modal',
    props: {
        show: {
            type: Boolean,
            default: false
        }
    },
    components: {
        ModalHeader,
        ModalBody,
        ModalFooter
    },
    inheritAttrs: false,
}
</script>

<style scoped>
.modal {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 9999;
    overflow-x: hidden;
    overflow-y: auto;
    outline: 0;
    pointer-events:none;
}

.modal-dialog {
    position: relative;
    width: auto;
    max-width: 500px;
    margin: 1.75rem auto;
    pointer-events: none;
}

.modal-content {
    position: relative;
    display: flex;
    flex-direction: column;
    width: 100%;
    pointer-events: auto;
    background-color: #fff;
    background-clip: padding-box;
    border: 1px solid rgba(0,0,0,.2);
    border-radius: .3rem;
    outline: 0;
}
</style>
