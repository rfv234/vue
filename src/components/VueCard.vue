<script setup>
defineProps({
    photo: {
        type: String,
        required: false
    },
    name: {
        type: String,
        required: true
    },
    about: {
        type: String,

        required: false
    }
})
</script>
<template>
    <div id="div1">
        <span>Моя страница</span><br>
        <span>Новости</span><br>
        <span>Мессенджер</span><br>
        <span>Звонки</span><br>
        <span>Друзья</span><br>
        <span>Сообщества</span><br>
        <span>Фотографии</span><br>
        <span>Музыка</span><br>
        <span>Видео</span><br>
        <span>Клипы</span><br>
        <span>Игры</span><br>
        <span>Стикеры</span><br>
        <span>Маркет</span><br>
        <hr class="hr1">
        <span>Сервисы</span><br>
        <span>Pay</span><br>
        <hr class="hr1">
        <span>Файлы</span><br>
        <span>Реклама</span><br>
    </div>
    <div id="div2">
        <img v-bind:src=photo v-if="photo" class="img">
        <img src="/src/assets/vopros.png" v-else class="img">
        <b v-if="name" class="bName">{{name}}</b>
        <b v-else class="bName">Имя</b>
        <b v-if="about" class="bAbout">{{about}}</b>
        <b v-else class="bAbout">О себе</b>
    </div>
    <div id="div3">
        <img v-bind:src=photo v-if="photo" class="img2">
        <img src="/src/assets/vopros.png" v-else class="img2">
        <span id="spDiv3">Что у вас нового?</span>
    </div>
    <div id="div4">
        <button class="butDiv4">Все записи</button>
        <button class="butDiv4">Мои записи</button>
        <button class="butDiv4">Архив записей</button>
        <hr class="hr2">
        <img v-bind:src=photo v-if="photo" class="img2">
        <img src="/src/assets/vopros.png" v-else class="img2">
        <b v-if="name" class="bName2">{{name}}</b>
        <b v-else class="bName2">Имя</b>
    </div>
</template>

<script>
export default {
    name: "VueCard",
}
</script>

<style scoped>
#div1 {
    position: absolute;
    left: 20px;
    top: 20px;
}
#div2 {
    border: solid 1px;
    height: 250px;
    width: 1000px;
    border-radius: 10px;
    left: 20%;
    background-color: #282828;
}
#div3 {
    position: absolute;
    border: solid 1px;
    height: 50px;
    width: 1000px;
    border-radius: 10px;
    left: 20%;
    background-color: #282828;
    top: 270px;
}
#div4 {
    position: absolute;
    border: solid 1px;
    height: 100px;
    width: 1000px;
    border-radius: 10px;
    left: 20%;
    background-color: #282828;
    top: 340px;
}
.bName {
    margin-left: 10px;
    margin-top: 60px;
    position: absolute;
    font-size: 20px;
}
.bName2 {
    left: 50px;
    top: 58px;
    position: absolute;
}
.img {
    margin: 25px;
    border-radius: 10px;
}
.bAbout {
    margin-left: 10px;
    margin-top: 100px;
    position: absolute;
    font-size: 15px;
}
.hr1 {
    margin: 20px;
    width: 90px
}
.hr2 {
    margin-top: 20px;
}
#spDiv3 {
    left: 50px;
    top: 12px;
    position: absolute;
}
.butDiv4 {
    border-radius: 10px;
    margin-left: 10px;
    top: 10px;
}
.img2 {
    width: 30px;
    height: 30px;
    border-radius: 10px;
    position: absolute;
    margin: 10px;
}
</style>
