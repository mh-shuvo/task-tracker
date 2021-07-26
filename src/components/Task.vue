<template>
    <div :class="[task.reminder ? 'reminder' : '','task']" @dblclick="$emit('toggle-reminder',task.id)">
        <h3>{{task.text}}
            <i @click="onDelete(task.id)" class="fas fa-times"></i>
        </h3>
        <p>{{task.day}}</p>
    </div>
</template>
<script>
export default {
    name: 'Task',
    props:{
        task:{
            type: Object
        }
    },
    methods: {
        onDelete(taskId){
           this.$emit('delete-task',taskId);
        }
    },
}
</script>
<style scope>
.fas {
  color: red;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>