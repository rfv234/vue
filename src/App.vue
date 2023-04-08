<script setup>
import {RouterLink, RouterView} from 'vue-router'
import VueCard from "./components/VueCard.vue";
import VueShop from "./components/VueShop.vue";
import VueTasks from "./components/VueTasks.vue";
import VueDifferentObjects from "./components/VueDifferentObjects.vue";
import VueModel from "./components/VueModel.vue";
import VueSelect from "./components/VueSelect.vue";

</script>

<template>
    <header>

        <div class="wrapper">
            <!--            <HelloWorld msg="You did it!" msg2="blablabla"/>-->
            <!--           <VueCard photo="/src/assets/images/chel.jpg"/>-->
            <!--            <VueShop/>-->
            <!--            <VueTasks/>-->
            <!--            <VueDifferentObjects/>-->
            <!--            <VueModel/>-->
            <VueSelect/>
        </div>
    </header>

</template>

<style scoped>

@media (min-width: 1024px) {

}
</style>
