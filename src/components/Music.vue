<template>
  <div class="music">
    <h3>My Songs</h3>
    <div class="songs">
      <div class="song" v-for="song in songs" :key="song.id">
        {{ song.Title }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Music",
  data() {
    return {
      songs: [],
    };
  },
  beforeMount() {
    fetch("http://161.35.199.153:1337/songs")
      .then((res) => res.json())
      .then((data) => {
        console.log(data);
        this.songs = data;
      });
  },
};
</script>

<style scoped>
.songs {
  display: flex;
}

.song {
  border: 1px solid red;
  width: calc(50% - 10px);
  margin: 10px;
  padding: 20px;
  box-sizing: border-box;
}
</style>
