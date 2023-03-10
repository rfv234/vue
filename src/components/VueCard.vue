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
    <div id="glav">
        Вконтакте
    </div>
    <div id="div1">
        <div v-for="item in menuItems" class="divItems">
            <span class="span1">{{ item }}</span><br>
        </div>
        <hr class="hr1">
        <div v-for="item in servicesItems" class="divItems">
            <span class="span1">{{ item.name }}</span><br>
        </div>
        <hr class="hr1">
        <div v-for="item in downItems" class="divItems">
            <span class="span1">{{ item.name }} </span>
            <span v-if="item.count" class="span1">({{ item.count }})</span><br>
        </div>
    </div>
    <div id="div2">
        <img v-bind:src=photo v-if="photo" class="img">
        <img src="/src/assets/images/vopros.png" v-else class="img">
        <b v-if="name" class="bName">{{ name }}</b>
        <b v-else class="bName">Имя</b>
        <b v-if="about" class="bAbout">{{ about }}</b>
        <b v-else class="bAbout">О себе</b>
    </div>
    <div id="div3">
        <img v-bind:src=photo v-if="photo" class="img2">
        <img src="/src/assets/images/vopros.png" v-else class="img2">
        <span id="spDiv3">Что у вас нового?</span>
    </div>
    <div id="div4">
        <button class="butDiv4" @click="show">Все записи</button>
        <button class="butDiv4">Мои записи</button>
        <button class="butDiv4">Архив записей</button>
        <hr class="hr2">
        <img v-bind:src=photo v-if="photo" class="img2">
        <img src="/src/assets/images/vopros.png" v-else class="img2">
        <b v-if="name" class="bName2">{{ name }}</b>
        <b v-else class="bName2">Имя</b>
    </div>
    <div>
        <div class="div5">
            <img v-for="image in menuImages" class="img3">
        </div>
    </div>
</template>

<script>
export default {
    name: "VueCard",
    data() {
        return {
            menuItems: [
                'Моя страница',
                'Новости',
                'Мессенджер',
                'Звонки',
                'Друзья',
                'Сообщества',
                'Фотографии',
                'Музыка',
                'Видео',
                'Клипы',
                'Игры',
                'Стикеры',
                'Маркет'
            ],
            menuImages: [
                {
                    src: '/src/assets/images/nature1.jpg'
                },
                {
                    src: '/src/assets/images/nature2.jpg'
                },
                {
                    src: '/src/assets/images/nature3.jpg'
                },
                {
                    src: '/src/assets/images/nature4.jpg'
                }
            ],
            servicesItems: [
                {
                    name: 'Сервисы',
                    color: 'blue'
                },
                {
                    name: 'Pay',
                    color: 'yellow'
                }
            ],
            downItems: [
                {
                    name: 'Файлы',
                    count: 1
                },
                {
                    name: 'Реклама'
                }

            ],
            alertMessage: 'привет'
        }
    },
    methods: {
        show: function () {
            let text = this.alertMessage;
            let newText = this.processMessage(text);
            alert(newText);
        },
        processMessage: function (text) {
            let firstSimbol = text[0].toUpperCase();
            let otherText = text.slice(1);
            let result = firstSimbol + otherText;
            return result;
        },
        days: function (dayNumber) {
            switch (dayNumber) {
                case 1:
                    return 'Понедельник';
                    break;
                case 2:
                    return 'Вторник';
                    break;
                case 3:
                    return 'Среда';
                    break;
                case 4:
                    return 'Четверг';
                    break;
                case 5:
                    return 'Пятница';
                    break;
                case 6:
                    return 'Суббота';
                    break;
                case 7:
                    return 'Воскресенье';
                    break;

            }
        }
    }
}
</script>

<style scoped>

.img3 {
    width: 200px;
    height: 200px;
    top: 500px;
    left: 500px;
    margin-left: 15px;
    margin-top: 30px;
}

#glav {
    background-color: #282828;
    text-align: center;
    color: white;
    font-size: 20px;
    height: 50px;
}

.span1 {
    margin-left: 5px;
    margin-top: 10px;
}

.divItems {
    margin-top: 15px;
    margin-left: 15px;
}

#div1 {
    position: absolute;
    font-size: 20px;
}

#div2 {
    position: absolute;
    border: solid 1px;
    height: 250px;
    width: 1000px;
    border-radius: 10px;
    left: 20%;
    background-color: #282828;
    margin: 15px;
    color: white;
}

#div3 {
    position: absolute;
    border: solid 1px;
    height: 50px;
    width: 1000px;
    border-radius: 10px;
    left: 20%;
    background-color: #282828;
    top: 320px;
    margin: 15px;
    color: white;
}

#div4 {
    position: absolute;
    border: solid 1px;
    height: 100px;
    width: 1000px;
    border-radius: 10px;
    left: 20%;
    background-color: #282828;
    top: 390px;
    margin: 15px;
    color: white;
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
