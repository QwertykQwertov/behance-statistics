<template>
  <div class="state-tooltip">
    <p class="date">Date: <span>{{ formatDate(props.info.argument) }}</span></p>
    <p class="download">Downloads: <span>{{ props.info.value }}</span></p>
  </div>
</template>
<script setup>
const props = defineProps({
  info: Object,
});
const formatDate = (value) => {
  let date = new Date(value);
  return new Intl.DateTimeFormat("ru-RU", { date: "short" }).format(date);
};
</script>
<style scoped>
.state-tooltip {
  height: 50px;
}
p, span {
  font-size: 14px;
}
span {
  font-weight: bold;
}
</style>
