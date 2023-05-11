<template>
<div>
    <label>Say something</label>
    <input type="something" v-model="something">
    <button @click="reactToIt">{{buttonLabel}}</button>
    <label> {{additionalLabel}}</label>
</div>
</template>

<script>
export default {
    data(){
        return {
            something:'',
        }
    },
    methods:{
        reactToIt(){
            this.$emit("yourText",this.something);
        }
    },
    props:{
        buttonLabel: String,
        additionalLabel: String,
    }
}
</script>
<style scoped>
</style>