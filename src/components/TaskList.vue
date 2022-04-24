<template>
    <ul  v-for="(task, index) in tasks" :key="index" class="list-group" :class="{ finished: task.finished }">
        <TaskItem 
            :task="task" 
            :index="index" 
            @delete-task="(index) => deleteTask(index)" 
            @check-task="(taskModel) => checkTask(taskModel)">
        </TaskItem>
    </ul>
</template>

<script>

import TaskItem from '@/components/TaskItem.vue';

export default {
    name: "TaskList",
    props: {
        items: Array
    },
    components: {
        TaskItem
    },
    data: () =>{
        return {
            tasks: []
        }
    },
    methods: {
        deleteTask(index) {
            this.tasks.splice(index,1);
        },
        checkTask(task){
            task.finished = !task.finished;
        }
    },
    mounted(){
        this.tasks = this.items;
    }
}
</script>