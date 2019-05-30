<template>
  <div>
    <p>teste</p>
    <button class="btn btn-dark" @click="logout">Sair</button>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  methods: {
    ...mapActions(["logout"])
  }
};
</script>

<style>
</style>
