<template>
  <v-dialog v-model="displayLoginWindow" max-width="600px" min-width="360px">
    <v-tabs v-model="currentTab" background-color="#72CFBF" icons-and-text dark grow>
      <v-tabs-slider color="white"></v-tabs-slider>
      <!-- Title -->
      <v-tab>
        <v-icon large>{{ 'mdi-account' }}</v-icon>
        <span class="caption py-1">Login</span>
      </v-tab>
      <v-tab>
        <v-icon large>{{ 'mdi-account-outline' }}</v-icon>
        <span class="caption py-1">Register</span>
      </v-tab>

      <v-tab-item>
        <!-- User Login -->
        <user-login @display-login-window="displayLoginWindow = $event"></user-login>
      </v-tab-item>
      <v-tab-item>
        <!-- User Register -->
        <user-register @display-login-window="displayLoginWindow = $event"></user-register>
      </v-tab-item>
    </v-tabs>
  </v-dialog>
</template>

<script>
  import UserLogin from './UserLogin';
  import UserRegister from './UserRegister';

  export default {
    components: { 
      UserLogin,
      UserRegister,
    },

    data() {
      return {
        currentTab: 0,
        displayLoginWindow: true,
      };
    },
  }
</script>
