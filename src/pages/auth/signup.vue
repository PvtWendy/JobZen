<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="12" md="6">
        <v-card>
          <v-card-title class="headline">Sign Up</v-card-title>
          <v-card-text>
            <v-form @submit.prevent="signUp">
              <v-text-field
                v-model="email"
                label="Email"
                type="email"
                required
              ></v-text-field>
              <v-text-field
                v-model="password"
                label="Password"
                type="password"
                required
              ></v-text-field>
              <v-btn type="submit" color="primary" block>Sign Up</v-btn>
            </v-form>
            <v-divider class="my-4"></v-divider>
            <v-btn
              @click="signInWithGoogle"
              color="red"
              block
              prepend-icon="mdi-google"
            >
              <template v-slot:prepend>
                <v-icon color="white" />
              </template>
              Sign Up with Google
            </v-btn>
            <v-btn
              @click="signInWithTwitter"
              color="blue"
              block
              prepend-icon="mdi-twitter"
            >
              <template v-slot:prepend>
                <v-icon color="white" />
              </template>
              Sign Up with Twitter
            </v-btn>
            <v-btn
              @click="signInWithFacebook"
              color="blue darken-3"
              block
              prepend-icon="mdi-facebook"
            >
              <template v-slot:prepend>
                <v-icon color="white" />
              </template>
              Sign Up with Facebook
            </v-btn>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import {
  signInWithFacebook,
  signInWithGoogle,
  signInWithTwitter,
  signUpWithEmail,
} from "@/firebase/auth";

export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    signUp() {
      signUpWithEmail(this.email, this.password);
    },
    signInWithGoogle() {
      signInWithGoogle();
    },
    signInWithTwitter() {
      signInWithTwitter();
    },
    signInWithFacebook() {
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
