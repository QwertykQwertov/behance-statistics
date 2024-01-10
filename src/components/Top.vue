<template>
  <div class="top-wrapper">
    <h2>Top 5 authors</h2>
    <ul class="top-list">
      <li class="top-list-item" v-for="author in authors" :key="author">
        <a class="author-link" :href="author.author_url" target="_blank">{{
          author.author
        }}</a>
        <p class="value">{{ customizeText(author.downloads) }}</p>
      </li>
    </ul>
  </div>
</template>
<script setup>
import { ref, onMounted } from "vue";

let authors = ref([]);
onMounted(() => {
  fetch("https://710ede90.artydev.ru/api/v1/top_authors/")
    .then((res) => res.json())
    .then(({ data }) => (authors.value = data));
});
const customizeText = (value) => {
  let formatValue = value;
  if (value >= 1000) {
    formatValue = (value / 1000).toFixed(2) + " K";
  }
  return formatValue;
};
</script>

<style lang="scss" scoped>
.top-wrapper {
  max-width: 350px;
  width: 95%;
}

.top-list {
  margin: 0;
  padding: 0;
}

.top-list-item {
  display: flex;
  justify-content: space-between;
  gap: 10px;
  margin: 10px 0;
  align-items: center;
}

.author-link {
  color: #4176fa;
  transition: 0.3s all;
  max-width: 74%;

  &:hover {
    color: #ee8d85;
  }
  text-decoration: none;
}
.value {
  margin: 0;
  color: #ee8d85;
}
</style>