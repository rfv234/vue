<template>
    <table>
        <tr>
            <td>Название</td>
            <td>Цена за штуку</td>
            <td>Количество</td>
            <td>Стоимость</td>
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
            <td>
                {{ good.count * good.price }}
            </td>
        </tr>
    </table>
    <h3>Итого (с учетом скидок): {{ result }}</h3>
    <br>
    <hr>
    <br>
    <div v-if="cart.length">
        <h4>Чек</h4>
        <ul>
            <li v-for="good in cart">
                {{ good.name }} - {{ good.count }}
            </li>
        </ul>
    </div>
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
        result: function () {
            let summa = 0;
            for (let i = 0; i < this.goods.length; i++) {
                if (this.goods[i].count >= 3) {
                    summa += this.goods[i].price * this.goods[i].count * 0.85;
                } else {
                    summa += this.goods[i].price * this.goods[i].count;
                }
            }
            if (summa >= 2000) {
                summa *= 0.7;
            }
            return summa;
        },
        cart: function () {
            let goodsInCart = [];
            for (let i = 0; i < this.goods.length; i++) {
                if (this.goods[i].count > 0) {
                    goodsInCart.push(this.goods[i]);
                }
            }
            return goodsInCart;
        }
    }
}
</script>

<style scoped>

</style>
