<template>
  <div class="limiter">
    <div class="container-login100 bckgrnd">
      <div class="wrap-login100">
        <span class="login100-form-logo">
          <img
            class="logo"
            src="../assets/logo-creche2.png"
            alt="Três crianças com as mãos dadas. Logo"
          >
        </span>

        <span class="login100-form-title p-b-34 p-t-27 fonte">Log in</span>

        <p v-if="loginError">{{ loginError }}</p>

        <form class="login100-form validate-form" @submit.prevent="loginSubmit">
          <div class="wrap-input100 validate-input">
            <input class="input100 fonte" type="email" placeholder="E-Mail" v-model="email">
          </div>

          <div class="wrap-input100 validate-input">
            <input class="input100 fonte" type="password" placeholder="Password" v-model="password">
          </div>

          <div class="container-login100-form-btn">
            <button class="login100-form-btn fonte" type="submit">Entrar</button>
          </div>

          <div v-if="loggingIn" class="container-loading">
            <img class="container-loading.img" src="../assets/loading.gif" alt="Loading Icon">
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState, mapActions } from "vuex";

export default {
  data() {
    return {
      email: "",
      password: ""
    };
  },
  computed: {
    ...mapState(["loggingIn", "loginError"])
  },
  methods: {
    ...mapActions(["doLogin"]),
    loginSubmit() {
      this.doLogin({
        email: this.email,
        password: this.password
      });
    }
  }
};
</script>

<style>
/* <style scoped lang="scss"> */
@import "../assets/css/main.css";
@import "../assets/css/util.css";
@import url("https://fonts.googleapis.com/css?family=Poppins&display=swap");

.fonte {
  font-family: "Poppins", sans-serif;
}

.bckgrnd {
  background-image: url("../assets/criancas-felizes-wallpaper.jpg");
  max-width: 100%;
  height: auto;
}

.logo {
  width: auto;
  height: 55%;
}

img.animated-gif {
  width: 40px;
  height: auto;
  margin-left: 44.5%;
}

.container-loading {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.3);
}

.container-loading.img {
  width: 2rem;
  height: 2rem;
}
</style>