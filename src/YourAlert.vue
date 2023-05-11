<template>
    <div>
        <label>Wanna an alert?</label>
        <input type="yourWords" v-model="yourWords">
        <button @click="reactToIt">Say something</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            yourWords:''
        }
    },
    methods:{
        reactToIt(){
            this.$emit("yourReaction",this.yourWords);
        }
    }
}
</script>
<style scoped>
</style>