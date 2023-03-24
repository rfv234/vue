import ToDoItem from "./components/ToDoItem.vue";
<template>
    <div id="glav">
        <form v-on:submit.prevent="addToDo">
            <label for="newTask">Добавить задачу:</label><br>
            <input id="newTask" placeholder="Новая задача" v-model="nextTitle">
            <button>Добавить</button>
        </form>
        <ul>
            <li
                is="ToDoItem"
                v-for="(todo, index) in todos"
                v-bind:key="todo.id"
                v-bind:title="todo.title"
                v-on:remove="todos.splice(index, 1)"
            >
                {{todo.title}}
            </li>
        </ul>
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
                    title: 'Вынести мусор'
                }
            ],
            nextId: 2,
            nextTitle: ''
        }
    },
    methods: {
        addToDo: function () {
            this.todos.push({
                id: this.nextId,
                title: this.nextTitle
            });
            this.nextTitle = '';
            this.nextId++;
        }
    }
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
