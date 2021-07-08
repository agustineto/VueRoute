<template>
  <Titulo texto="Curso de Vue JS" />

  <!-- <button @click="consumirApi">Consumir APi</button> -->
  <div v-for="item in arrayBlog" :key="item.id">
      <router-link :to="`/blog/${item.id}`">{{ item.title }}</router-link>
  </div>

</template>

<script>
import Titulo from '../components/Titulo.vue'
export default {
  props: {

  },
    components: {
      Titulo
  },
   data(){
      return{
        arrayBlog:[]
      }
  },
  methods:{
      async consumirApi(){
          try{
              const data = await fetch(`https://jsonplaceholder.typicode.com/posts`)
              const arrayData = await data.json()
              this.arrayBlog = arrayData
              //console.log(arrayData)
          }catch(error){
              console.log(error)
          }

      }
  },
  created(){
    this.consumirApi()
  }

}
</script>

<style></style>
