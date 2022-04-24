<template>
    <li class="list-group-item">
        {{ task.text }}
        <button class="btn btn-sm btn-danger right-button" @click="$emit('deleteTask', index)">
            <i class="fa fa-times"></i>
        </button>
        <button class="btn btn-sm btn-success right-button" @click="$emit('checkTask', task)">
            <i class="fa fa-check"></i>
        </button>
    </li> 
</template>

<script>
export default {
    name: "TaskItem",
    props: ['task', 'index'],
    emits: ['deleteTask','checkTask']
}
</script>