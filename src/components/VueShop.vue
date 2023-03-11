<template>
    <table>
        <tr>
            <td>Название</td>
            <td>Цена</td>
            <td>Количество</td>
        </tr>
        <tr v-for="good in goods">
            <td>
                {{ good.name }}
            </td>
            <td>
                {{ good.price }}
            </td>
            <td>
                <button @click="addGood(good)">+</button>
                {{ good.count }}
                <button @click="removeGood(good)">-</button>
            </td>
        </tr>
    </table>
    <h3>Итого: {{ result }}</h3>
</template>

<script>
export default {
    name: "VueShop",
    data() {
        return {
            goods: [
                {
                    name: 'Яблоки',
                    price: 100,
                    count: 0
                },
                {
                    name: 'Бананы',
                    price: 60,
                    count: 0
                },
                {
                    name: 'Груши',
                    price: 150,
                    count: 0
                },
                {
                    name: 'Гранаты',
                    price: 300,
                    count: 0
                }
            ]
        }
    },
    methods: {
        addGood: function (good) {
            good.count++;
        },
        removeGood: function (good) {
            if (good.count > 0) {
                good.count--;
            }
        }
    },
    computed: {
        result: function () {
            let summa = 0;
            for (let i = 0; i < this.goods.length; i++) {
                summa += this.goods[i].price * this.goods[i].count;
            }
            return summa;
        }
    }
}
</script>

<style scoped>

</style>
