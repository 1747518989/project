<template>
    <div>
        <div>这是a组件</div><br/>
        <router-link to="/b">跳转到b主键</router-link>
        <button @click="toA">跳转到b主键，传送query参数</button>
        <button @click="toAa">跳转到b主键</button>
        <button @click="toAcom">跳转到b主键,传送params参数</button>
        <a-child :toChild="test"></a-child>
    </div>
</template>

<script>
import AChild from './a-child.vue'

export default {
    components: {
        AChild
    },
    data () {
        return {
            test:'传入组件内部的参数'
        }
    },
    methods: {
        toA () {
            this.$router.push({path:"/b",query: {name: 'tom',age: '10',id: 'arr'}})
        },
        toAa () {
            this.$router.replace('/b')
        },
        toAcom () {
            this.$router.push({name:'b',params:{newName:'jack',newAge:'20'}})
        }
    }
}
</script>
