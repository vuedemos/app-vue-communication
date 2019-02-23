<template>
    <div class="component-a">
        <button @click="toggle">显示警告框</button>
        <ComponentB :show="isShow" :title="title" :content="content" @on-submit="submit" />
    </div>
</template>

<script>
import ComponentB from './ComponentB'
import ComponentC from './ComponentC'

export default {
    name: 'ComponentA',
    components: {
        ComponentB
    },
    methods: {
        submit () {
            this.isShow = false
        },
        toggle () {
            this.isShow = true
        }
    },
    data () {
        return {
            isShow: false,
            title: '我是标题',
            content: '我是内容'
        }
    }
}
</script>

<style scoped>
    
    
</style>
