<template>
  <div class="article">
    <h2>{{ article.title }}</h2>
    <img :src="baseURL + img.url" v-for="img in images" :key="img.id" />
    <button v-on:click="changePhoto">Next</button>
    <p>
      {{ article.content }}
    </p>
  </div>
</template>

<script>
export default {
  name: "Article",
  data() {
    return {
      article: {},
      viewingId: 0,
      baseURL: process.env.VUE_APP_BASE_URL,
    };
  },
  computed: {
    images() {
      return this.article.images
        ? this.article.images.filter(
            (x) => x.id === this.viewingIds[this.viewingId]
          )
        : [];
    },
    viewingIds() {
      return this.article.images ? this.article.images.map((x) => x.id) : [];
    },
  },
  beforeMount() {
    fetch(process.env.VUE_APP_BASE_URL + "/articles/" + this.$route.params.id)
      .then((res) => res.json())
      .then((data) => (this.article = data));
  },
  methods: {
    changePhoto() {
      this.viewingId + 1 === this.viewingIds.length
        ? (this.viewingId = 0)
        : this.viewingId++;
    },
  },
};
</script>

<style scoped>
img {
  width: 250px;
}
</style>
