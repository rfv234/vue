<script setup>
defineProps({
    text: {
        type: String,
        required: false
    }
})
</script>
<template>
    <span v-if="text">{{ text }}</span>
    <span v-else>привет</span>
</template>

<script>
export default {
    name: "VueGreetings"
}
</script>

<style scoped>

</style>
