<template>
    <div class="container">
        <div class="p-5 mb-4 bg-light rounded-3">
            <TaskTitle title="Lista de Tareas"></TaskTitle>
            <TaskForm @add-task="(value) => addTask(value)" :modelValue="model.task"></TaskForm>
            <TaskList :items="tasks" ></TaskList>
        </div> 
    </div>
</template>

<script>

import TaskList from "@/components/TaskList.vue";
import TaskForm from "@/components/TaskForm.vue";
import TaskTitle from "@/components/TaskTitle.vue";

export default {
    name: 'TaskMain',
    components: {
        TaskTitle,
        TaskList,
        TaskForm
    },
    data: () => {
        return {
            model: {
                task: ""
            },
            tasks: [
                {
                    text:"Aprender Vuejs",
                    finished: false
                },
                {
                    text:"Aprender Laravel",
                    finished: false
                },
                {
                    text:"Aprender SQL",
                    finished: false
                }
            ]
        }
    },
    methods: {
        addTask(value) {

            console.log(value);

            let text = value;
            this.tasks.push({
                text,
                finished: false
            })
            
            this.model.task = "";
        },
        checkTask(task) {
            task.finished = !task.finished;
        }
    }
}
</script>

<style>
    .right-button {
        float: right;
    }
    .finished {
        color: gray;
        text-decoration: line-through;
    }
</style>