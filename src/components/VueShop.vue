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
                },
                {
                    name: 'Сливы',
                    price: 80,
                    count: 0
                },
                {
                    name: 'Арбузы',
                    price: 450,
                    count: 0
                },
                {
                    name: 'Апельсины',
                    price: 150,
                    count: 0
                },
                {
                    name: 'Мандарины',
                    price: 100,
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
        result: function (good) {
            let summa = 0;
            let discount = 30;
            if (good.count > 3) {
                let result_discount = good.price - discount;
                for (let i = 0; i < this.goods.length; i++) {
                    summa += result_discount * this.goods[i].count;
                }
            }
            else {
                for (let i = 0; i < this.goods.length; i++) {
                    summa += this.goods[i].price * this.goods[i].count;
                }
            }
            return summa;
        }
    }
}
</script>

<style scoped>

</style>
ю
