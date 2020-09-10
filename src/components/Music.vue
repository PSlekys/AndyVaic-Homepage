<template>
  <div class="music">
    <h3>My Songs</h3>
    <div class="songs">
      <div class="song" v-for="song in songs" :key="song.id">
        <h4 class="title">{{ song.Title }}</h4>
        <audio controls>
          <source :src="baseURL + song.Song.url" />
          Your browser does not support this audio player
        </audio>
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
      baseURL: process.env.VUE_APP_BASE_URL,
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
  background: rgba(164, 205, 209, 0.5);
  box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.2);
  width: calc(50% - 10px);
  margin: 10px;
  padding: 20px;
  box-sizing: border-box;
}

h3 {
  font-size: 1.8em;
  text-align: center;
}

.title {
  text-align: center;
}

audio {
  width: 100%;
}
</style>
