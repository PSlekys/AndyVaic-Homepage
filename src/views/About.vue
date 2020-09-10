<template>
  <div class="about">
    <h1>This is an about page</h1>
    <ArticleList />
  </div>
</template>

<script>
import ArticleList from "../components/ArticleList";

export default {
  name: "About",
  components: { ArticleList },
};
</script>
