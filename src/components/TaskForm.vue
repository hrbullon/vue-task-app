<template>
    <div class="input-group mb-3">
        <input type="text" class="form-control" :model="task" @keyup.enter="$emit('addTask', $event.target.value)" placeholder="Ingrese nueva tarea">
        <button class="btn btn-primary" @click="$emit('addTask', task)" type="button">
            <i class="fa fa-plus"></i> Agregar
        </button>
    </div>
</template>

<script>
export default {
    name: "TaskForm",
    props: ['modelValue'],
    emits: ['addTask'],
    data: () => {
        return {
            task: ""
        }
    },
    mounted(){
        this.task = this.modelValue;
    }
}
</script>
