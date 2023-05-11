<template>
    <form @submit.prevent="addNewComponent()">
        <h3>Add something</h3>
        <input type="text" v-model="newThing.name">
        <button>Add me</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            newThing: {}
        };
    },
    methods: {
        addNewComponent() {
            this.$emit('added', this.newThing);
            this.newThing= {};
        }
    }
}
</script>