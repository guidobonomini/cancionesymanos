<template>
  <div class="hello">
    <h1>{{ lyrics }}</h1>
  </div>
</template>

<script>
export default {
  name: "Lyrics",
  props: {
    lyrics: String
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
