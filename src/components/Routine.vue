<template>
  <div class="container my-2">
    <div class="row">
      <div class="col">
        <div class="card bg-dark text-white">
          <div class="card-header bg-secondary">{{ routine.time }} routine</div>
          <div class="card-body">
            <div class="h5">Tasks ({{routine.tasks.length}})</div>
            <div class="list-group">
              <div v-for="task in routine.tasks" :key="task.title" class="list-group-item">
                <div class="row justify-content-between">
                    <div class="col-10">~ {{ task.title }} - {{ task.duration }}</div>
                    <div class="col-2 align-items-end"> <button class="btn btn-danger btn-sm"> delete</button> </div>
                </div>
                
              </div>
            </div>
            <div>
            <button @click="addTask" class="btn btn-primary my-2">Add task to routine</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

import { ref } from 'vue';


const props = defineProps({
    routine: {
        type: Object,
        required:true

    }}
)
function addTask() {
    console.log('adding task*************');
    props.routine.tasks.push({
        title: "Temporary task", duration:"5 minutes"
    })

}

</script>

