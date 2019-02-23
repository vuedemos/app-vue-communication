<template>
    <div class="modal-footer">
        <button class="btn btn-secondary" data-dismiss="modal" @click="close">{{ secondaryButtonContent }}</button>
        <button class="btn btn-primary" @click="save">{{ primaryButtonContent }}</button>
    </div>
</template>

<script>
export default {
    name: 'ModalFooter',
    props: {
        secondaryButtonContent: {
            type: String,
            default: 'Close'
        },
        primaryButtonContent: {
            type: String,
            default: 'Save'
        }
    },
    inheritAttrs: false,
    methods: {
        save () {
            this.$emit('on-save')
        },
        close () {
            this.$emit('on-close')
        }
    },
    mounted () {
        console.log('ModalFooter',this.$attrs, this.$listeners)
    }
}
</script>

<style scoped>
.modal-footer {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    padding: 1rem;
    border-top: 1px solid #e9ecef;
}

.btn {
    -webkit-appearance: button;
    display: inline-block;
    font-weight: 400;
    text-align: center;
    white-space: nowrap;
    vertical-align: middle;
    user-select: none;
    border: 1px solid transparent;
    padding: .375rem .75rem;
    font-size: 1rem;
    line-height: 1.5;
    border-radius: .25rem;
    transition: color .15s ease-in-out,background-color .15s ease-in-out,border-color .15s ease-in-out,box-shadow .15s ease-in-out;
}

.btn-secondary {
    color: #fff;
    background-color: #6c757d;
    border-color: #6c757d;
}

.btn-primary {
    color: #fff;
    background-color: #007bff;
    border-color: #007bff;
}

.btn-secondary:hover {
    color: #fff;
    background-color: #5a6268;
    border-color: #545b62;
}

.btn-primary:hover {
    color: #fff;
    background-color: #0069d9;
    border-color: #0062cc;
}

.btn:not(:disabled):not(.disabled) {
    cursor: pointer;
}

.btn-secondary:not(:disabled):not(.disabled):active {
    color: #fff;
    background-color: #545b62;
    border-color: #4e555b;
}

.btn-secondary:not(:disabled):not(.disabled):active:focus {
    box-shadow: 0 0 0 0.2rem rgba(108,117,125,.5);
}

.btn-primary:not(:disabled):not(.disabled):active {
    color: #fff;
    background-color: #0062cc;
    border-color: #005cbf;
}

.btn-primary:not(:disabled):not(.disabled):active:focus {
    box-shadow: 0 0 0 0.2rem rgba(0,123,255,.5);
}
.modal-footer>:not(:last-child) {
    margin-right: .25rem;
}
</style>
