<template>
  <v-app-bar>
    <div class="header">
      <v-toolbar-title @click="goHome">
        <div class="title">
          <v-icon left>mdi-briefcase-variant</v-icon>
          <span>JobZen</span>
        </div>
      </v-toolbar-title>

      <div class="button-group">
        <v-btn variant="flat" color="primary" to="/login"> Log In </v-btn>
        <v-btn text="true" to="/signup">Sign Up</v-btn>
      </div>
    </div>
  </v-app-bar>
</template>

<script setup>
import { useRouter } from "vue-router";

const router = useRouter();
const goHome = () => {
  router.push("/");
};
</script>

<style>
.title {
  cursor: pointer;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 5px;
  width: fit-content;
}

.header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 0 10%;
}
.button-group {
  display: flex;
  gap: 10px;
}
</style>
