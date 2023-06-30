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

    <div class="card bg-dark text-white">
      <div class="card-header bg-secondary">My Profile</div>
      <div class="card-body">
        <h5 class="card-title">First name: {{profile.firstName}}</h5>
        <h5 class="card-title">last name: {{profile.lastName}}</h5>
        <p class="card-text">Github link: <a href={{profile.githubLink}}>{{ profile.githubUsername }}</a></p>
      </div>
    </div>
    <hr>
    <br>
    <h2>Inside this:</h2>
    <li>Lists: <a class="btn btn-primary btn-sm" href="/todos">Todos example</a></li>

  </main>
</template>
