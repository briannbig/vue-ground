<script setup>
import { reactive, computed } from 'vue'
import Routine from '@/components/Routine.vue'

const routines = reactive([
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

// basic computed properties
const routineRecommendation = computed(() => {
  return routines.length <= 2 ? 'Routine seems cool' : 'Routine needs optimization'
})

function addRoutine(event) {
  // `event` is the native DOM event
    routines.push({
      time: 'evening',
      tasks: [
        { title: 'Commit work done', duration: '10 mins' },
        { title: 'Review work done', duration: '10 mins' },
      ]
    })
  
}
</script>

<template>
  <main>
    <h1>My routines</h1>
    <h3>{{ routineRecommendation }}</h3>
     <Routine v-for="routine in routines" :key="routine.time" :routine="routine" />

    <button class="btn btn-primary" @click="addRoutine">Add routine</button>
  </main>
</template>
