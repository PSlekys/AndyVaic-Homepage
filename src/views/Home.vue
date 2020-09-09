<template>
  <div class="home">
    <Header />
    <Music />
  </div>
</template>

<script>
import Header from "../components/Header";
import Music from "../components/Music";

export default {
  name: "Home",
  components: { Header, Music },
};
</script>
