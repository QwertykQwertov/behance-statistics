<template>
  <div class="state-tooltip">
    <p class="date">Date: <span>{{ formatDate(props.info.argument) }}</span></p>
    <p class="download">Downloads: <span>{{ props.info.value }}</span></p>
  </div>
</template>
<script setup>
// import { computed } from "vue";

const props = defineProps({
  info: Object,
});
console.log(props.info);
const formatDate = (value) => {
  let date = new Date(value);
  return new Intl.DateTimeFormat("ru-RU", { date: "short" }).format(date);
};
</script>
<style>
.state-tooltip {
  height: 50px;
}
span {
  font-weight: bold;
}
</style>
