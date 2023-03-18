<template>
    <li>
        {{title}}
        <button v-on:click="$emit('remove')">Удалить</button>
    </li>
</template>

<script>
export default {
    name: "ToDoItem",
    data() {
        return {
            title: ''
        }
    },
    props: [
        'title'
    ]
}
</script>

<style scoped>

</style>
