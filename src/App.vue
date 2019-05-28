<template>
  <v-app>
    <v-content>
      <v-btn color="primary" dark class="login-btn" @click="showForm('login')"
        >Login</v-btn
      >
      <v-btn
        color="primary"
        dark
        class="register-btn"
        @click="showForm('register')"
        >Register</v-btn
      >
    </v-content>
    <div id="blur">
      <div class="login">
        <p class="close" @click="closeForm('login')">X</p>
        <Login />
      </div>
      <div class="register">
        <p class="close" @click="closeForm('register')">X</p>
        <Register />
      </div>
    </div>
  </v-app>
</template>

<script>
import Login from "@/components/Login";
import Register from "@/components/Register";

export default {
  name: "App",
  components: {
    Login,
    Register
  },
  methods: {
    showForm(el) {
      document.querySelector("#blur").style.display = "block";
      document.querySelector(`.${el}`).style.display = "block";
    },
    closeForm(el) {
      document.querySelector("#blur").style.display = "none";
      document.querySelector(`.${el}`).style.display = "none";
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.login-btn,
.register-btn {
  border-radius: 10px;
}

#blur {
  display: none;
  width: 100vw;
  height: 100vh;
  position: absolute;
  z-index: 9;
  background: rgba(15, 15, 15, 0.9);
}

.login {
  display: none;
  width: 350px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
  text-align: center;
}

.register {
  display: none;
  width: 350px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
  text-align: center;
}

.close {
  color: #ffffff;
  font-size: 30px;
  cursor: pointer;
}

.v-text-field > .v-input__control > .v-input__slot:before {
  border-style: none;
}
</style>
