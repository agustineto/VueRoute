<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Titulo texto="Pagina de inicio con Vue"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Titulo from '../components/Titulo.vue'

export default {
  data () {
    return {
    }
  },
  name: 'Home',
  components: {
    Titulo
  }
}
</script>
