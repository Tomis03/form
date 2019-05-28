<template>
  <div id="login-form">
    <v-card id="main">
      <h2 class="register-title">visato</h2>
      <h3 class="register-text">Create an account to apply</h3>
      <v-card-text>
        <v-form>
          <v-text-field
            v-model="fullname"
            name="fullname"
            label="Your full name"
            clearable
            class="register-fullname"
          ></v-text-field>
          <v-text-field
            v-model="email"
            name="email"
            label="Your email address"
            clearable
            class="register-email"
          ></v-text-field>
          <v-text-field
            :append-icon="show ? 'visibility' : 'visibility_off'"
            :rules="[rules.required, rules.min]"
            :type="show ? 'text' : 'password'"
            name="input-10-2"
            label="Your password"
            class="register-pass"
            @click:append="show = !show"
          ></v-text-field>
          <v-btn block color="info" class="register-btn text-capitalize"
            >Sign Up</v-btn
          >
        </v-form>
        <div class="policy">
          By creating an account you are agreeing to our
          <a href="#">T&C's</a> and <a href="#">Privacy Policy</a>.
        </div>
      </v-card-text>
    </v-card>
    <p class="create-account">
      Already have an account?
      <a href="#">Log in</a>
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: true,
      rules: {
        required: value => !!value || "Required.",
        min: v => v.length >= 8 || "Min 8 characters"
      }
    };
  }
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: #ffffff;
  font-weight: bold;
}

#main {
  background: #f1f1f1;
  padding: 10px 10px 0 10px;
  border-radius: 10px;
}

.register-title {
  color: #3ba2f4;
  font-size: 30px;
}

.register-text {
  font-size: 14px;
}

.register-pass,
.register-email,
.register-fullname {
  padding: 7px 15px 0 15px;
  margin: 10px 0;
  border-radius: 10px;
  background: #ffffff;
  height: 45px;
  border-style: none;
}

.policy {
  text-align: center;
  width: 270px;
  font-size: 11px;
  margin: auto;
}

.policy a {
  color: #000000;
}

.register-btn {
  height: 45px;
  border-radius: 10px;
  margin: 25px 0 15px 0;
}

.create-account {
  color: #ffffff;
  margin-top: 20px;
}
</style>
