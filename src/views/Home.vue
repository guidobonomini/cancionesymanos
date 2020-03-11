<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Buscador/>
  </div>
</template>

<script>
// @ is an alias to /src
import Buscador from '@/components/Buscador.vue'

export default {
  name: 'Home',
  components: {
    Buscador
  }
}
</script>
