<script setup>
import { ref } from 'vue'
  const drawer = ref(null)
</script>

<template>
  <v-app >
    <!-- add navbar -->
    <router-view/>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ drawer: null }),
  }
</script>