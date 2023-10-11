<template>
  <div class="download-wrapper">
    <h2>Downloads</h2>
    <div class="download-list">
      <div class="download-list-item">
        <p class="download-title">Total:</p>
        <span class="total-value">{{ customizeText(total) }}</span>
      </div>
      <div class="download-list-item">
        <p class="download-title">Weekly:</p>
        <span class="weekly-value">{{ customizeText(weekly) }}</span>
      </div>
      <div class="download-list-item">
        <p class="download-title">Today:</p>
        <span class="daily-value">{{ customizeText(daily) }}</span>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref, onMounted } from "vue";
let total = ref();
let weekly = ref();
let daily = ref();

onMounted(() => {
  fetch("https://710ede90.artydev.ru/api/v1/total/")
    .then((res) => res.json())
    .then(({ data }) => {
      total.value = data.total;
      weekly.value = data.weekly;
      daily.value = data.daily;
    });
});
const customizeText = (value) => {
  let formatValue = value;
  if (value >= 1000) {
    formatValue = (value / 1000).toFixed(2) + " K";
  }
  return formatValue;
};
</script>


<style scoped>
.download-wrapper {
  width: 25%;

}
.download-list {
  margin: 0 auto;
  max-width: 65%;
  font-size: 36px;
}
.download-list-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.download-title {
  margin: 10px 0;
}
.total-value {
  color: #ee8d85;
}
.weekly-value {
  color: #eabc47;
}
.daily-value {
  color: #4176fa;
}
</style>