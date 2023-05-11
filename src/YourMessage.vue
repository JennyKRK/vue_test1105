<template>
<div>
    <label>Say something</label>
    <input type="something" v-model="something">
    <button @click="reactToIt">Say something</button>
</div>
</template>

<script>
export default {
    data(){
        return {
            something:''
        }
    },
    methods:{
        reactToIt(){
            this.$emit("yourText",this.something);
        }
    }
}
</script>
<style scoped>
</style>