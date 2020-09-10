<template>
  <div class="header">
    <header>
      <h2>Mylėsiu tave, net jei žemės nebebus</h2>
    </header>
    <div class="triangle"></div>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
header {
  min-height: 80vh;
  background-image: url("../assets/andy_vaic_1.jpg");
  background-size: cover;
  background-attachment: fixed;
  box-sizing: border-box;
  position: relative;
}

h2 {
  position: absolute;
  top: 50%;
  left: 1em;
  transform: translate(0, -50%);
  font-size: 2em;
  background: rgba(0, 0, 0, 0.5);
  color: white;
  padding: 0.5em 0.6em;
  margin: 0;
}

.triangle {
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 0 0 80px 100vw;
  border-color: transparent transparent transparent #fff;
  transform: rotateX(180deg);
  position: relative;
  top: -80px;
}
</style>
