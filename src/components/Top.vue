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
let authors = [
  {
    author: "Đốm Đốm",
    author_url: "https://www.behance.net/ddooms",
    downloads: 9598,
  },
  {
    author: "Liz Tulentsova",
    author_url: "https://www.behance.net/lizt",
    downloads: 8333,
  },
  {
    author: "Marcela Soares",
    author_url: "https://www.behance.net/mrclssoares",
    downloads: 3398,
  },
  {
    author: "Elena Nalabordina",
    author_url: "https://www.behance.net/svoyalena",
    downloads: 789,
  },
  {
    author: "Anastasia Bikmulina",
    author_url: "https://www.behance.net/anquari",
    downloads: 674,
  },
];
const customizeText = (value) => {
  let formatValue = value;
  if (value >= 1000) {
    formatValue = (value / 1000).toFixed(1) + " K";
  }
  return formatValue;
};
</script>

<style lang="scss" scoped>
.top-wrapper {
  width: 25%;
}

.top-list {
  font-size: 30px;
  margin: 0;
  padding: 0;
  // list-style: circle;
}

.top-list-item {
  display: flex;
  gap: 10px;
  margin: 10px 0;
  align-items: center;
}

.author-link {
  color: #4176fa;
  transition: 0.3s all;

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