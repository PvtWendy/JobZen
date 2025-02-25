<template>
  <v-app-bar>
    <div class="header">
      <v-toolbar-title>
        <v-icon left>mdi-briefcase-variant</v-icon>
        Jobzen
      </v-toolbar-title>

      <div class="button-group">
        <v-btn text="true" variant="flat" color="primary"> Log In </v-btn>
        <v-btn text="true">Sign Up</v-btn>
      </div>
    </div>
  </v-app-bar>
</template>

<style>
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
