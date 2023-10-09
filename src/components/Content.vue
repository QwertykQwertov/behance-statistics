<script setup>
import { ref } from "vue";
import Chart from "./Chart.vue";
import Download from "./Download.vue";
import Top from "./Top.vue";

defineProps({
  msg: String,
});

const count = ref(0);
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
    display: flex;
    justify-content: space-around;
  }
</style>
