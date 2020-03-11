<template>
  <div class="hello">
    <input v-model="cancion" placeholder="Canción" />
    <input v-model="artista" placeholder="Artista" />
    <button v-on:click="callGeniusApi()">Buscar</button>
    <Lyrics :lyrics="letra"/>
  </div>
</template>

<script>
import Lyrics from "@/components/Lyrics.vue";
import { getLyrics } from "genius-lyrics-api";

export default {
  name: "Buscador",
  data() {
    return {
      cancion: "",
      artista: "",
      letra: ""
    };
  },
  components:{
    Lyrics
  },
  methods: {
    callGeniusApi() {
      const options = {
        apiKey: "eF0K6vGqSt5ZEWv6UUwhaTBweVBnQ2gmV8uEQ5R76FXRmD1xyGcUna0dV_cdkEWS", // genius developer access token
        title: this.cancion,
        artist: this.artista,
        optimizeQuery: true
      };
      getLyrics(options).then(lyrics => {
        this.letra = lyrics;
      })
    }
  }
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
