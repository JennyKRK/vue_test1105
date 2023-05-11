<template>
    <p class="firstPart">Hello {{name}}</p>
</template>

<script>
export default {
    data(){
        return{
            name: "my friend"
        }
    }
}
</script>

<style>
p.firstPart {
    font-size: 2em;
    text-align: center;
    color: blue;
}
</style>
