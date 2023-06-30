<template>
  <div class="container my-2">
    <div class="row">
      <div class="col">
        <div class="card">
          <div class="card-header">{{ routine.time }} routine</div>
          <div class="card-body">
            <div class="h1"></div>
            <div class="list-group">
              <li v-for="task in routine.tasks" :key="task.title" class="list-group-item">
                ~ {{ task.title }} - {{ task.duration }}
              </li>
            </div>
            <div class="text-center">
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
        title: "Added task", duration:"5 minutes"
    })

}

</script>

