<template>
    <input type="checkbox" id="filter1" v-model="filters" value="Производитель">
    <label for="filter1">Производитель</label>
    <input type="checkbox" id="filter2" v-model="filters" value="Тип питания">
    <label for="filter2">Тип питания</label>
    <input type="checkbox" id="filter3" v-model="filters" value="Страна производства">
    <label for="filter3">Страна производства</label>
    <input type="checkbox" id="filter4" v-model="filters" value="Стоимость">
    <label for="filter4">Стоимость</label>
    <br>
    <div id="div1">
        <p v-for="filter in filters">{{ filter }}</p>
    </div>
    <hr>
    <div>
        <ul>
            <div v-for="product in products">
                <li>{{ product.name }}</li>
            </div>

        </ul>
    </div>
</template>

<script>
export default {
    name: "VueModel",
    data() {
        return {
            filters: [],
            products: [
                {
                    name: 'телевизор',
                    'Тип питания': '220В',
                    'Стоимость': 30000,
                    isActive: true
                },
                {
                    name: 'пылесос',
                    'Страна производства': 'Россия',
                    'Стоимость': 20000,
                    isActive: true
                },
                {
                    name: 'пк',
                    'Производитель': 'hp',
                    'Стоимость': 60000,
                    isActive: true
                },
                {
                    name: 'процессор',
                    'Производитель': 'intel',
                    'Стоимость': 15000,
                    isActive: true
                }
            ]
        }
    },
    computed: {
        productsToShow: function () {
            // for (let filter in this.filters) {
            //     for (let i = 0; i < this.products.length; i++) {
            //         if (!this.products[i].hasOwnProperty(filter)) {
            //             this.products[i].isActive = false;
            //             console.log(this.products);
            //         }
            //     }
            // }
            console.log(this.filters);
            return this.products.filter(function (product) {
                for (let i = 0; i < this.filters.length; i++) {
                    if (product.hasOwnProperty(this.filters[i])) {
                        return true;
                    } else {
                        return false;
                    }
                }
            });
        }
    }
}
</script>

<style scoped>
#div1 {
    border: solid 2px;
    width: 500px;
    height: 200px;
}
</style>
