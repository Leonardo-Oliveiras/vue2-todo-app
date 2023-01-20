<template>
    <div class="task-grid">
        <template v-if="tasks.length">
            <Task v-for="(task, id) in tasks" 
            :key="task.name" 
            @taskDeleted="$emit('taskDeleted', id)"
            :task="task"
            />
        </template>
        <p v-else class="all-done-tasks">You finish all your tasks :)</p>
    </div>
</template>

<script>
import Task from './Task.vue'

export default {
    components: { Task },
    props: {
        tasks: { type: Array, required: true }
    }
}
</script>

<style>
    .task-grid {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }

    .task-grid .task {
        margin: 10px;
    }

    .all-done-tasks{
        color: #AAA;
        font-size: 1.7rem;
    }

</style>