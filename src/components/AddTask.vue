<template>
<form class='add-form' @submit="onSubmit">
    <div class="form-control"> 
        <label>Task</label>
        <input type="text" v-model="text" name="text" placeholder="Add task" />
    </div>
    <div class="form-control">
        <label>Date and Time</label>
        <input type="text" v-model="time" name="time" placeholder="Add date" />
    </div>
    <div class="form-control form-control-checkbox">
        <label>Set Reminder</label>
        <input type="checkbox" class="checkbox" v-model="reminder" name="reminder" />
    </div>
    <div class="form-control">
        <Button class="btn save-task-btn" type="submit" text="SAVE TASK" color="rgb(95, 179, 143)" />
    </div>
</form>
</template>

<script>
import Button from './Button';

export default {
  name: 'AddTask',
  data(){
      return {
          text: '',
          time: '',
          reminder: false,
      };
  },
  methods: {
      onSubmit(e){
          e.preventDefault();

          if(!this.text){
              alert('Tipe something in the text input!!!');
              return;
          }

          let newTask = {
              text: this.text,
              time: this.time,
              reminder: this.reminder,
          }
          
          this.$emit( 'add-task', newTask);

          this.text = '';
          this.time = '';
          this.reminder = false;
      }
  },
  components: {
      Button,
  }
}



</script>

<style scoped>
.add-form {
    margin: 20px;
}

.form-control {
    display: flex;
    justify-content: space-between;
    margin: 5px 0;
}

.form-control-checkbox input {
margin-top: 5px;
font-weight: none;
}

.save-task-btn {
    width: 100%;
    margin: 0;
}

label {
    font-weight: bold;
}

</style>