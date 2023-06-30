<script setup>
import { ref } from 'vue'

const profile = ref({
  firstName: 'Brian',
  lastName: 'Barasa',
  githubUsername: 'briannbig',
  githubLink: 'https://github.com/briannbig'
})
</script>

<template>
  <main>
    <h1>My vue learning repo</h1>
    <h2>My Profile</h2>
    <p>First name: {{ profile.firstName }}</p>
    <p>Last name: {{ profile.lastName }}</p>
    <p>
      Github link: <a href={{profile.githubLink}}>{{ profile.githubUsername }}</a>
    </p>
    <hr>
    <br>
    <h2>Inside this:</h2>
    <li>Lists: <a href="/todos">Todos example</a></li>

  </main>
</template>
