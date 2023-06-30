<script setup>
import { ref } from 'vue'
import Navbar from '@/components/Navbar.vue'
  const drawer = ref(null)
</script>

<template>
  <v-app >
    <Navbar/>
    <router-view/>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ drawer: null }),
  }
</script>