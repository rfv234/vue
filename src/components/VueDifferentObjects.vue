<template>
    <h1>Список покупок</h1>
    <div class="wrapper">
        <table v-for="(item, index) in items">
            <tr>
                <th>Пункты описания</th>
                <th>Описание</th>
            </tr>
            <tr v-for="(param, name) in item">
                <td>{{ name }}</td>
                <td>{{ param }}</td>
            </tr>
            <button @click="tomusor(item, index)" class="Musor">В корзину</button>
        </table>
    </div>
    <h2>Корзина</h2>
    <div class="wrapper">
        <table v-for="(item, index) in itemsInMusor">
            <tr v-for="(param, name) in item">
                <td>{{ name }}</td>
                <td>{{ param }}</td>
            </tr>
            <button @click="outmusor(item, index)" class="Musor">Убрать из корзины</button>
        </table>
    </div>
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
            itemsInMusor: []
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
h1 {
    text-align: center;
}

h2 {
    text-align: center;
}

.wrapper {
    display: flex;
    flex-wrap: wrap;
}

table {
    font-family: "Lucida Sans Unicode", "Lucida Grande", Sans-Serif;
    font-size: 14px;
    border-radius: 10px;
    border-spacing: 0;
    text-align: center;
    margin: 20px;
}

th {
    background: #BCEBDD;
    color: white;
    text-shadow: 0 1px 1px #2D2020;
    padding: 10px 20px;
}

th, td {
    border-style: solid;
    border-width: 0 1px 1px 0;
    border-color: white;
}

td {
    padding: 10px 20px;
    background: #F8E391;
}

.Musor {
    font-weight: 700;
    color: white;
    text-decoration: none;
    padding: .8em 1em calc(.8em + 3px);
    border-radius: 3px;
    background: rgb(64, 199, 129);
    box-shadow: 0 -3px rgb(53, 167, 110) inset;
    transition: 0.2s;
}

.Musor:hover {
    background: rgb(53, 167, 110);
}

.Musor:active {
    background: rgb(33, 147, 90);
    box-shadow: 0 3px rgb(33, 147, 90) inset;
}
</style>
