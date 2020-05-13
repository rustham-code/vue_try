<template>
  <div id="app">
  <ul class="todo-list">
    <li class="title">
      <b>Lista de tareas</b>
      <div>
         <input type="text" v-model="newName"> 
         <button @click="addTask()"> create </button>
      </div>
    </li>
    <li v-for="task in tasks" :class="{'complete': task.selected}">
       <input type="checkbox" v-model="task.selected"/>
       {{ task.name}}
    </li>
  </ul>  
</div>
</template>

<script>
new Vue({
  el: "#app",
  data: {
    newName: '',
		tasks: [
      {name : "ir a clase de prog web 1", selected: false},
		  {name : "hacer el ejercicio de vue", selected: true},
		  {name : "hacer las ramas de git", selected: true},
      {name : "push al repositorio", selected: false},
      {name : "hacer los request", selected: false},
		]
  },
  methods: {
 		addTask(){
    	let task = {
      	name: this.newName,
        selected: false
      }
    	this.tasks.push(task);
      this.newName = '';
    }
  }
})
</script>

<style>
.todo-list {
	 padding: 20px;
	 border: 1px solid gray;
	 border-radius: 10px;
	 margin: 10px auto;
	 width: 400px;
}
 .todo-list .title {
	 margin-bottom: 10px;
}
 .todo-list .complete {
	 text-decoration: line-through;
}
</style>

