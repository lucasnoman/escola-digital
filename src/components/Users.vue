<template>
  <div class="container-fluid">
    <nav class="navbar navbar-dark bg-dark" style="background-color: #e3f2fd;">
      <a class="navbar-brand text-white">Sistema de Gerenciamento</a>
      <form class="form-inline">
        <button class="btn btn-outline-success my-2 my-sm-0" @click="logout">Sair</button>
      </form>
    </nav>

    <div class="jumbotron jumbotron-fluid text-center">
      <h1 class="jumbotron-heading">Págida do Professor</h1>
      <p class="lead text-muted">Aqui encontrará informações sobre disciplinas e alunos.</p>
    </div>

    <div class="container">
      

      <Cards />
      <!-- <CrudDisciplina/> -->
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import Cards from "./cards/Cards.vue";
import CrudDisciplina from "./crud/CrudDisciplina.vue";

export default {
  methods: {
    ...mapActions(["logout"])
  },
  components: {
    Cards,
    CrudDisciplina
  }
};
</script>

<style>
</style>
