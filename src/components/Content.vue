<script setup>
import { defineAsyncComponent } from "vue";
const Chart = defineAsyncComponent(() =>
  import('./Chart.vue')
)
// import Chart from "./Chart.vue";
import Download from "./Download.vue";
import Top from "./Top.vue";
</script>

<template>
  <div class="flex-container">
    <Chart />
    <Download />
    <Top />
  </div>
</template>

<style scoped>
  .flex-container{
    width: 95%;
    margin: 0 auto;    
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }
</style>
