<script setup>
  import { Authenticator } from "@aws-amplify/ui-vue";
  import "@aws-amplify/ui-vue/styles.css";

  import { Amplify } from 'aws-amplify';
  import config from './amplifyconfiguration.json';
  Amplify.configure(config);
</script>

<template>
  <authenticator v-slot="{ user, signOut }">
      <h1>Hello {{ user.username }}!</h1>
      <button @click="signOut">Sign Out</button>
  </authenticator>
</template>

<style>
.amplify-button--primary {
  background: linear-gradient(
    to right,
    var(--amplify-colors-green-80),
    var(--amplify-colors-orange-40)
  );
}
.background-customizable {
  box-shadow: 0px 2px 20px rgba(0, 0, 0, 20%), 0 0 0 10000px #eee;
}
.amplify-label {
  color: var(--amplify-colors-orange-80);
}

.amplify-tabs__item{
  color: linear-gradient(
    to left,
    var(--amplify-colors-green-80),
    var(--amplify-colors-orange-40)
  );
}

.amplify-tabs__panel{
background: var(--amplify-colors-red-10);
}
footer{
  background: var(--amplify-colors-red-10); 
}
</style>