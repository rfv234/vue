<script setup>
import {RouterLink, RouterView} from 'vue-router'
import VueCard from "./components/VueCard.vue";

</script>

<template>
    <header>

        <div class="wrapper">
<!--            <HelloWorld msg="You did it!" msg2="blablabla"/>-->
           <VueCard photo="/src/assets/images/chel.jpg" name="Андрей Фамилия"/>
        </div>
    </header>

</template>

<style scoped>

@media (min-width: 1024px) {

}
</style>
