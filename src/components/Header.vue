<template>
    <header>
        <h1>{{title}}</h1>
        <Button v-show="homePage" @btn-click="$emit('toggle-add-task')" class='btn' :text="showAddTask ? 'CLOSE FORM' : 'ADD TASK'" :color="showAddTask ? 'rgb(214, 130, 182)' : 'rgb(65, 76, 73)'" />
    </header>
</template>

<script>
import Button from './Button'; 

export default {
    name: 'Header',
    props: {
        title: String,
        showAddTask: Boolean,
    },
    components: {
        Button,
    },
    computed: {
        homePage(){
         if(this.$route.path === '/'){
             return true;
         } else {
             return false;
         }
        }
        
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 20px;
    color:rgb(6, 123, 72);
}
</style>