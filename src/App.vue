<script setup>
import { ref } from 'vue';


const data = ref([])

const addData = async () => {
  data.value.push("Test")
  const apiData = await fetch("http://192.168.56.102:8000/spreads")
  console.log(await apiData);
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
