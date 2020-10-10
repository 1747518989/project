<template>
    <div>
        <div>这是b组件</div><br/>
        <router-link to="/a">跳转到a主键</router-link>
        <button @click="toB">跳转到a主键</button>
        <button @click="toBb">跳转到a主键</button>
        <button @click="toBcom">获取query参数</button>
        <button @click="toBdom">获取params参数</button>
    </div>
</template>

<script>
export default {
    data () {
        return {}
    },
    methods: {
        toB () {
            this.$router.push({path:"/a"})
        },
        toBb () {
            this.$router.replace('/a')
        },
        toBcom () {
            console.log(this.$route.query)
        },
        toBdom () {
            console.log(this.$route.params)
        }
    }
}
</script>
