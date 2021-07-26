<template>
    <div :key="task.id" v-for="task in tasks">
        <Task @toggle-reminder="$emit('toggle-reminder',task.id)" @delete-task="DeleteTask" :task="task"/>
    </div>
</template>
<script>
import Task from './Task.vue'
export default {
    name:"Tasks",
    props:{
        tasks:Array
    },
    components:{
        Task
    },
    methods: {
        DeleteTask(id){
            this.$emit('delete-task',id)
        }
    },
}
</script>