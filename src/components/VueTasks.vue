import ToDoItem from "./components/ToDoItem.vue";
<template>
    <div id="glav">
        <form v-on:submit.prevent="addToDo">
            <label for="newTask">Добавить задачу:</label><br>
            <input id="newTask" placeholder="Новая задача" v-model="nextTitle">
            <button>Добавить</button>
        </form>
        <ul>
            <div v-for="(todo, index) in todos">
                <li
                    v-show="todo.visible"
                    is="ToDoItem"
                    v-bind:key="todo.id"
                    v-bind:title="todo.title"
                    v-on:remove="todos.splice(index, 1)"
                >
                    {{ todo.title }}
                    <button @click="hide(todo)">Удалить</button>
                </li>
            </div>
        </ul>
        <button @click="showAll">Показать все</button>
    </div>
</template>

<script>
export default {
    name: "VueTasks",
    data() {
        return {
            todos: [
                {
                    id: 1,
                    title: 'Вынести мусор',
                    visible: true
                }
            ],
            nextId: 2,
            nextTitle: ''
        }
    },
    methods: {
        addToDo: function () {
            if (this.nextTitle != '') {
                this.todos.push({
                    id: this.nextId,
                    title: this.nextTitle,
                    visible: true
                });
                this.nextTitle = '';
                this.nextId++;
            }
        },
        hide: function (todo) {
            todo.visible = false;
        },
        showAll: function () {
            for (let i = 0; i < this.todos.length; i++) {
                this.todos[i].visible = true;
            }
        }
    },
    computed: {}
}
</script>

<style scoped>
#glav {
    width: 300px;
    border: solid 1px;
    position: absolute;
    left: 45%;
    top: 100px;
    padding: 15px;
    font-size: 17px;
    background-color: lightblue;
    border-radius: 10px;
}
</style>
