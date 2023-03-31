<template>
    <h1>Список покупок</h1>
    <table v-for="(item, index) in items">
        <tr v-for="(param, name) in item">
            <td>{{ name }}</td>
            <td>{{ param }}</td>
        </tr>
        <button @click="tomusor(item, index)">В корзину</button>
    </table>
    <h3>Корзина</h3>
    <table v-for="(item, index) in itemsInMusor">
        <tr v-for="(param, name) in item">
            <td>{{ name }}</td>
            <td>{{ param }}</td>
        </tr>
        <button @click="outmusor(item, index)">Убрать из корзины</button>
    </table>
</template>

<script>
export default {
    name: "VueDifferentObjects",
    data() {
        return {
            items: [
                {
                    name: 'пылесос',
                    price: 10000,
                    model: 'lg'
                },
                {
                    name: 'яблоки',
                    price: 100,
                    weight: 2,
                    kind: 'галла'
                },
                {
                    name: 'футболка',
                    price: 1000,
                    brand: 'levy',
                    color: 'white'
                },
                {
                    name: 'кроссовки',
                    price: 4000,
                    brand: 'puma',
                    color: 'black'
                },
                {
                    name: 'pc',
                    price: 60000,
                    model: 'hp pavilion'
                },
                {
                    name: 'картофель',
                    price: 400,
                    weight: '3',
                    kind: 'Бронницкий'
                },
                {
                    name: 'процессор',
                    price: 12000,
                    model: 'intel core'
                }
            ],
            itemsInMusor: [

            ]
        }
    },
    methods: {
        tomusor: function (item, index) {
            this.itemsInMusor.push(item);
            this.items.splice(index, 1);
        },
        outmusor: function (item, index) {
            this.items.push(item);
            this.itemsInMusor.splice(index, 1);
        }
    }
}
</script>

<style scoped>
table {
    border: solid 1px;
    margin: 20px;
}

tr {
    border: solid 1px;
}

td {
    border: solid 1px;
}
</style>
