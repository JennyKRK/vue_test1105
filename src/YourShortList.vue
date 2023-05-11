<template>
    <div>
        <NewItemForm @added="(newItem) => addNewItem(newItem)"></NewItemForm>
        <MyItemsList :myItems="myItems"></MyItemsList>
    </div>
</template>

<script>
import NewItemForm from "@/NewItemForm.vue";
import MyItemsList from "@/MyItemsList.vue";


export default {
    components: {MyItemsList, NewItemForm},
    data() {
        return {
            myItems: []
        };
    },
    methods: {
        addNewItem(newItem) {
            this.myItems.push(newItem);
        }
    }
}
</script>