<template>
    <div class="tasks-grid">
        <template v-if="tasks.length">
            <task v-for="(task, i) in tasks" :key="task.name" 
            @deleteTask="$emit('deleteTask', i)"
            @changeState="$emit('changeState', i)"
            :task="task" />
        </template>
        <p class="no-tasks" v-else>
            Sua vida está em dia :)
        </p>
    </div>
</template>

<script>
import Task from './Task.vue'

export default {
    components: {Task},
    props: {
        tasks: { type: Array, required: true}
    }
}
</script>

<style>
    .tasks-grid {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }
    .tasks-grid .task {
        margin: 10px;
    }
    .no-task {
        color: #aaa;
        font-size: 1.7rem;
    }
</style>