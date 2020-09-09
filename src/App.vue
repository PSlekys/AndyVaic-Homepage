<template>
  <div id="app">
    <Navigation />
    <router-view />
  </div>
</template>

<script>
import Navigation from "./components/Navigation";

export default {
  components: { Navigation },
};
</script>

<style>
div#app {
  font-family: "Barlow", sans-serif;
}
</style>
