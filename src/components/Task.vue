<template>
    <div 
      @dblclick="$emit('toggle-reminder', task.id)"
      :class="[task.reminder ? 'reminder' : '', 'task']">
        <h3>{{task.text}}
            <i @click="$emit('delete-task', task.id)" class="fas fa-trash"></i>
        </h3>
        <h5>{{task.time}}</h5>
    </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object,
  },
}
</script>

<style scoped>
.task {
    margin-top: 2%;
    background-color: rgb(68, 144, 115);
    border-radius: 4px;
    padding: 10px 15px;
}

.task.reminder {
    border-left: 5px solid rgb(76, 65, 73);
}

.task h3 {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.task h3 i {
    margin-top: 3%;
    color: rgb(214, 130, 182);
}

</style>