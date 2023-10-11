<template>
  <div class="download-wrapper">
    <h2>Downloads</h2>
    <div class="download-list">
      <div class="download-list-item">
        <p class="download-title">
          Total: <span class="total-value">{{ customizeText(total) }}</span>
        </p>
      </div>
      <div class="download-list-item">
        <p class="download-title">
          Weekly: <span class="weekly-value">{{ customizeText(weekly) }}</span>
        </p>
      </div>
      <div class="download-list-item">
        <p class="download-title">
          Today: <span class="daily-value">{{ customizeText(daily) }}</span>
        </p>
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
  font-size: 36px;
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