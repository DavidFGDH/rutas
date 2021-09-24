<template>
  <div class="home">
    <img width="200" alt="Vue logo" src="../assets/logouts.png">
    <Titulo texto="David Garcia Cano"/>
    <Titulo texto="Universidad tecnologica de Salamanca"/>
    <Titulo texto="Tecnologías de la Información, Área Desarrollo de Software Multiplataforma"/>
    <Titulo texto="David Garcia Cano"/>
    <Titulo texto="TIS 4A"/>

  </div>
</template>

<script>
// @ is an alias to /src

import Titulo from "../components/Titulo";
export default {
  name: 'Home',
  components: {
    Titulo
  }
}
</script>
