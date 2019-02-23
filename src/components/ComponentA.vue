<template>
    <div class="component-a">
        <ComponentB :name="name" :age="age"  @on-test1="onTest1" @on-test2="onTest2" />
    </div>
</template>

<script>
import ComponentB from './ComponentB'

export default {
    name: 'ComponentA',
    components: {
        ComponentB
    },
    data () {
        return {
            name: '大漠_w3cplus',
            age: 23
        }
    },
    methods: {
        onTest1 () {
            console.log('test1 runing...')
        },
        onTest2 () {
            console.log('test2 running...')
        }
    }
}
</script>

<style scoped>
    
    
</style>
