<template>
    <table v-if="myItems.length > 0">
        <thead>
        <tr>
            <th>Your items:</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="myItem in myItems" :key="myItem.name">
            <td>{{ myItem.name }}</td>
        </tr>
        </tbody>
    </table>
</template>

<script>
    export default {
        props: {myItems: Array}
    }
</script>