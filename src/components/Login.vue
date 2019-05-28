<template>
  <div id="login-form">
    <v-card id="main">
      <h2 class="login-title">visato</h2>
      <h3 class="login-text">Log in to your account</h3>
      <v-card-text>
        <v-form>
          <v-text-field
            v-model="email"
            name="email"
            label="Your email address"
            clearable
            class="login-email"
          ></v-text-field>
          <v-text-field
            :append-icon="show ? 'visibility' : 'visibility_off'"
            :rules="[rules.required, rules.min]"
            :type="show ? 'text' : 'password'"
            name="input-10-2"
            label="Your password"
            class="login-pass"
            @click:append="show = !show"
          ></v-text-field>
          <v-btn block color="info" class="login-btn text-capitalize"
            >Log in</v-btn
          >
        </v-form>
      </v-card-text>
    </v-card>
    <p class="create-account">
      Don't have an account?
      <a href="#">Sign up</a>
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

.login-title {
  color: #3ba2f4;
  font-size: 30px;
}

.login-text {
  font-size: 14px;
}

.login-pass,
.login-email {
  padding: 7px 15px 0 15px;
  margin: 10px 0;
  border-radius: 10px;
  background: #ffffff;
  height: 45px;
  border-style: none;
}

.login-btn {
  height: 45px;
  border-radius: 10px;
  margin: 25px 0 15px 0;
}

.create-account {
  color: #ffffff;
  margin-top: 20px;
}
</style>
