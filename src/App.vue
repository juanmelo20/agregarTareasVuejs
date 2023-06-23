<script setup>
import TaskComponent from './components/TaskComponent.vue';
import { ref } from 'vue';
const taskList = ref([
    'Levantarse',
    'Cepillarse',
    'Alimentarse',
    
  ])
  
let newTask

function addTask() {
taskList.value.unshift(newTask);
newTask=undefined
}
const deleteTask =(index)=>{
taskList.value.splice(index,1)
}
</script>

<template>

<div class="px-4 py-3 mx-auto mt-12 space-y-2 overflow-hidden
rounded shadow-md bg-gray-100 w-96">
  <h1 class="text-xl font-bold">
    Lista de tareas
  </h1>
  <div class="flex" >
    <input type="text" class="w-4/5 h-8 px-2 py-1 border border-r-0
    border-green-600 text-lg font-semibold text-center rounded
    rounded-r-none" v-model="newTask">
    <span class="w-1/5 h-8 py-1 text-white border-green-500 bg-green-700 text-center rounded rounded-l-none
     leading-none hover:bg-green-500 hover:cursor-pointer" @click="addTask">
      +
    </span>
  </div>
  <TaskComponent v-for="(task,index) in taskList" 
  :name="task" :index="index"
  @deleteTask="deleteTask"/>
</div>
</template>
