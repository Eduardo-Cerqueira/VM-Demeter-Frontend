<script setup>
import { ref } from 'vue';


const data = ref([])

const addData = () => {
  data.value.push("Test")
}
</script>

<template>
  <main>
    <button @click="addData">GENERATE</button>
    <div class="data-wrapper">
      <div class="data-card" v-for="el, index in data" :key="index">
      {{ el }} 
    </div>
    </div>
    
  </main>
</template>

<style scoped>

</style>
