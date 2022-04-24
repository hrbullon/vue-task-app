<template>
    <div class="input-group mb-3">
        <input type="text" class="form-control" v-model="task" @keyup.enter="emitAdd()" placeholder="Ingrese nueva tarea">
        <button class="btn btn-primary" @click="emitAdd()" type="button">
            <i class="fa fa-plus"></i> Agregar
        </button>
    </div>
</template>

<script>
export default {
    name: "TaskForm",
    emits: ['addTask'],
    data: () => {
        return {
            task: ""
        }
    },
    methods: {
        emitAdd(){
            this.$emit('addTask', this.task);
            this.task = "";
        }
    }
}
</script>
