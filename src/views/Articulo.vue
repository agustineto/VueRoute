<template>
  <Titulo texto='Mi primer articulo con Vuejs'/>
  <h4>Parametro: {{ $route.params.id}}</h4>
  <div>
    <hr>
    <h2>{{articulo.title}}</h2>
    <p>{{articulo.body}}</p>
  </div>
</template>

<script>
import Titulo from '../components/Titulo'
export default {

  components: {
      Titulo
  },  data () {
    return {
      articulo:{}
    }
  },
  methods:{
    
    async consumirArticulo(){
          try{
              const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
              const arrayData = await data.json()
              this.articulo = arrayData
          }catch(error){
              console.log(error)
          }

      }
  },
  created(){
    this.consumirArticulo()
  }
  

}
</script>

<style>

</style>