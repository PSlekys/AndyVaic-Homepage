<template>
  <div class="navigation">
    <router-link to="/">
      <h1>Andy Vaic</h1>
    </router-link>

    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <span class="social">
        <a href="#">FB</a>
        <a href="#">IG</a>
      </span>
    </nav>
  </div>
</template>

<script>
export default {
  name: "Navigation",
};
</script>

<style scoped>
.navigation {
  padding: 0 1em;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav a:not(:last-child) {
  margin-right: 10px;
}
</style>
