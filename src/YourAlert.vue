<template>
    <div>
        <label>Wanna an alert?</label>
        <input type="yourWords" v-model="yourWords">
        <button @click="reactToIt">{{funnyLabel}}</button>
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
    },
    props:{
        funnyLabel: String,
    }
}
</script>
<style scoped>
</style>