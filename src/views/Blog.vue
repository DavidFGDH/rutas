<template>
  <div>
    <Titulo texto="Proyecto con rutas"/>
    <br>
    <div v-for="item in arrayBlog" :key="item.id">
      <router-link :to="`/blog/${item.id}`">
        {{item.title}}
      </router-link>
    </div>
  </div>
</template>

<script>
import Titulo from "../components/Titulo";
export default {
  components: {Titulo},
  data(){
    return{
      arrayBlog:[]
    }
  },
  methods: {
    async consumirApi(){
        try{
          const data = await fetch('https://jsonplaceholder.typicode.com/posts')
          const array = await data.json()
          this.arrayBlog = array
          console.log('consumido',array)
        }catch (e) {
          console.log(e)
        }
    }
  },
  created() {
    this.consumirApi()
  }
}
</script>

<style scoped>

</style>