<script setup>
import { ref, computed } from 'vue'

const todos = ref([
  {
    time: 'morning',
    tasks: [
      { title: 'Wake up', duration: '5 mins' },
      { title: 'Make bed', duration: '15 mins' },
      { title: 'Benediction', duration: '15 mins' },
      { title: 'Workout', duration: '25 mins' },
      { title: 'Shower', duration: '10 mins' },
      { title: 'Take breakfast', duration: '30 mins' },
      { title: 'Commute to work', duration: '10 mins' }
    ]
  },
  {
    time: 'noon',
    tasks: [
      { title: 'Create github CI', duration: '15 mins' },
      { title: 'Commit work done', duration: '10 mins' },
      { title: 'Take lunch', duration: '45 mins' },
      { title: '30 minutes walk', duration: '30 mins' },
      { title: 'Prepare for meeting', duration: '5 mins' }
    ]
  }
])
</script>

<template>
  <main>
    <h1>My Todos</h1>
    <li v-for="todo in todos" v-bind:key="todo">
      {{ todo.time }}
      <br />
      <!-- basic computation inside templates -->
      Complexity: - {{ todo.tasks.length > 5 ? 'more' : 'less' }}
      <br />
      <hr />
      <ol v-for="task in todo.tasks" v-bind:key="task">
        [-]
        {{
          task.title
        }}
        -
        {{
          task.duration
        }}
      </ol>
    </li>
  </main>
</template>
