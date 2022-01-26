<template>
    <header>
        <h1>{{title}}</h1>
        <Button @ShowForm="$emit('toggle-add-task')" :label="showAddTask ? 'Close':'Add Task'" :color="showAddTask ? 'red' : 'green'" />
    </header>
</template>
<script>
import Button from './Button.vue';
export default{
    name:'Header',
    props:{
        title:{
            type:String,
            default:"Task Tracker"
        },
        showAddTask:{
            type:Boolean
        }
    },
    components:{
        Button
    },
    methods: {
        
    },
}
</script>
<style scoped>
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>
