<template>
  <div class="article-list">
    <div class="article" v-for="article in articles" :key="article.id">
      <h3>{{ article.title }}</h3>
      <router-link :to="'/article/' + article.id">Read More</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "ArticleList",
  data() {
    return {
      articles: [],
    };
  },
  beforeMount() {
    fetch(`${process.env.VUE_APP_BASE_URL}/Articles`)
      .then((res) => res.json())
      .then((data) => (this.articles = data));
  },
};
</script>

<style scoped>
.article {
  background: rgba(164, 205, 209, 0.5);
  box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.2);
  padding: 20px;
  margin-bottom: 20px;
  box-sizing: border-box;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
