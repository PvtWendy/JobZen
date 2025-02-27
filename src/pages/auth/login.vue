<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="12" md="6">
        <v-card>
          <v-card-title class="headline">Login</v-card-title>
          <v-card-text>
            <v-form @submit.prevent="login">
              <v-text-field
                label="Email/User"
                v-model="email"
                required
              ></v-text-field>
              <v-text-field
                label="Password"
                type="password"
                v-model="password"
                required
              ></v-text-field>
              <v-btn type="submit" color="primary" block>Login</v-btn>
            </v-form>
            <v-divider class="my-4"></v-divider>
            <v-btn
              @click="loginWithGoogle"
              color="red"
              block
              prepend-icon="mdi-google"
            >
              <template v-slot:prepend>
                <v-icon color="white" />
              </template>
              Login with Google
            </v-btn>
            <v-btn
              @click="loginWithTwitter"
              color="blue"
              block
              prepend-icon="mdi-twitter"
            >
              <template v-slot:prepend>
                <v-icon color="white" />
              </template>
              Login with Twitter
            </v-btn>
            <v-btn
              @click="loginWithFacebook"
              color="blue darken-3"
              block
              prepend-icon="mdi-facebook"
            >
              <template v-slot:prepend>
                <v-icon color="white" />
              </template>
              Login with Facebook
            </v-btn>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import {
  signInWithEmail,
  signInWithFacebook,
  signInWithGoogle,
  signInWithTwitter,
} from "@/firebase/auth";

export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    login() {
      signInWithEmail(this.email, this.password);
    },
    loginWithGoogle() {
      signInWithGoogle();
    },
    loginWithTwitter() {
      signInWithTwitter();
    },
    loginWithFacebook() {
      signInWithFacebook();
    },
  },
};
</script>

<style scoped>
.v-btn {
  margin-bottom: 10px;
}
</style>
