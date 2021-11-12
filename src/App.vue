<template>
<div class="container">
   <Header :showAddTask='showAddTask' @toggle-add-task='toggleAddTask' title='Task Manager'/>
   <router-view :showAddTask='showAddTask'></router-view>
   <Footer />
</div>

 
</template>

<script>
import Header from './components/Header';
import Footer from './components/Footer';


export default {
  name: 'App',
  components: {
    Header,
    Footer
  },

  data(){
   return { 
     tasks: [], 
     showAddTask: false,
     }
  },

   methods: {
    toggleAddTask(){
      this.showAddTask=!this.showAddTask;
  },
 }
}

</script>

<style>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family:Arial, Helvetica, sans-serif;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid rgb(76, 65, 72);
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  width: 100px;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:hover {
  color: rgb(186, 17, 124);
}

.btn:focus {
  color: rgb(6, 123, 72);
}

.btn-block {
  display: block;
  width: 100%;
}
</style>
