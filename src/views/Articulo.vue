<template>
  <div>
    <Titulo texto="Articulo"/>
    <h2>Parámetro: {{$route.params.id}}</h2>
    <div class="container">
    <div class="card mb-3" style="max-width: 300px">
      <img src="../assets/logouts.png"  class="card-img-top" alt=""/>
      <div class="card-body">
        <h5 class="card-title">Titulo</h5>
        <p class="card-text">{{articulo.title}}</p>
      </div>
      <ul class="list-group list-group-flush">
        <span>Descripcion</span>
        <li class="list-group-item">{{articulo.body}}</li>
      </ul>
      <div class="card-body">
        <a href="/blog" class="btn btn-warning">Atras</a>
        |
        <router-link to="/blog" class="btn btn-primary">Atras</router-link>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
import Titulo from "../components/Titulo";
export default {
  components: {Titulo},
  data(){
    return{
      articulo:{}
    }
  },
  methods:{
    async cosumitArticulo(){
      try{
        const data= await fetch('https://jsonplaceholder.typicode.com/posts/'+this.$route.params.id)
        const art = await  data.json()
        this.articulo = art
      }catch (e) {
        console.log(e)
      }
    }
  },
  created() {
    this.cosumitArticulo()
  }
}
</script>

<style scoped>

</style>