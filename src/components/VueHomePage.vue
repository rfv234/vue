<template>
    <h2 class="tasks">{{ name }}</h2>
    <h3 class="tasks">{{ job }}</h3>
    <div v-for="task in tasks" class="divs">
        <strong class="tasks" v-if="task.status!=='в разработке'">{{ task.taskName }}</strong>
        <input class="tasks" v-if="task.status=='в разработке'" v-model="task.taskName">
        <div class="tasks">
            <span v-if="task.status!=='в разработке'">{{ task.description }}</span>
            <input v-if="task.status=='в разработке'" v-model="task.description">
        </div>
        <select class="tasks" v-bind:name="task.taskName" v-model="task.status">
            <option
                v-for="tasksStatus in tasksStatuses"
                v-bind:selected="tasksStatus==task.status"
                v-bind:value="tasksStatus">
                {{ tasksStatus }}
            </option>
        </select>
    </div>
    <button @click="addTask()">Добавить задачу</button>
</template>

<script>
export default {
    name: "VueHomePage",
    data() {
        return {
            name: 'имя сотрудника',
            job: 'должность',
            tasks: [
                {
                    taskName: 'тестовая задача',
                    description: 'описание задачи',
                    status: 'отложена',
                    user_id: 1,
                }
            ],
            tasksStatuses: [
                'в разработке',
                'выполняется',
                'на проверке',
                'выполнена',
                'отложена',
                'отменена'
            ]
        }
    },
    methods: {
        addTask: function () {
            this.tasks.push({
                taskName: 'тестовая задача ' + (this.tasks.length + 1),
                description: 'описание задачи ',
                status: 'в разработке',
                user_id: 1,
            });
        }
    }
}

</script>

<style scoped>
.divs {
    margin-left: 15px;
    padding: 5px;
    border: solid 2px;
    margin-top: 10px;
}

.tasks {
    margin: 10px;
}
</style>
