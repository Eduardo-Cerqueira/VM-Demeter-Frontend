<script setup>
import { ref } from 'vue';


const data = ref([])

const urlIp = `${import.meta.env.VITE_API_IP}`
const urlPort = `${import.meta.env.VITE_API_PORT}`

const addData = async () => {
  data.value.push("Test")
  console.log(`http://${urlIp}:${urlPort}/spreads`);
  const apiData = await fetch(`http://${urlIp}:${urlPort}/spreads`)
  
  console.log(apiData);
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
