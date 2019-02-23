<template>
    <div class="component-c">
        <div class="alert">
            <h2>{{ title }}</h2>
            <div class="alert-content">{{ content }}</div>
            <button @click="submit">确定</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ComponentC',
    props: {
        title: {
            type: String,
            default: '警告标题'
        },
        content: {
            type: String,
            default: '警告内容'
        }
    },
    inheritAttrs: false,
    methods: {
        submit () {
            this.$emit('on-submit')
        }
    },
    mounted () {
        console.log('ComponentC',this.$attrs, this.$listeners)
    }
}
</script>

<style scoped>
    .alert {
        position: fixed;
        left: 50%;
        top: 50%;
        width: 300px;
        height: 200px;
        border-radius: 10px;
        text-align: center;
        background-color: #fff;
        transform: translate(-50%, -50%);
    }
</style>
