<template>
    <li>
        {{title}}

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
