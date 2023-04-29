<template>
    <select v-model="selected">
        <option disabled value="">Выберите один из вариантов</option>
        <option v-for="option in options" v-bind:value="option.value">{{ option.text }}</option>
    </select>
    <div>
        <ul>
            <li v-for="product in products[selected]">{{ product }}</li>
        </ul>
    </div>

</template>

<script>
export default {
    name: "VueSelect",
    data() {
        return {
            selected: '',
            options: [
                {
                    text: 'фрукты',
                    value: 0
                },
                {
                    text: 'овощи',
                    value: 1
                },
                {
                    text: 'ягоды',
                    value: 2
                }
            ],
            products: [
                ['яблоки', 'бананы'],
                ['картофель', 'морковь'],
                ['арбуз', 'малина']
            ]
        }
    }
}
</script>

<style scoped>

</style>
