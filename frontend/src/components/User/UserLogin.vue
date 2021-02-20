<template>
  <v-card class="pa-4">
    <v-row>
      <!-- Email -->
      <v-col cols="12">
        <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>
      </v-col>
      <!-- Password -->
      <v-col cols="12">
        <v-text-field v-model="password" :rules="[passwordRules.required, passwordRules.min]"
                      :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                      :type="showPassword ? 'text' : 'password'"
                      label="Password" hint="At least 8 characters" counter
                      @click:append="showPassword = !showPassword">
        </v-text-field>
      </v-col>
      <!-- Submit -->
      <v-col class="d-flex justify-end pr-8" cols="12">
        <v-btn class="text-capitalize" large rounded color="success" @click="submitLogin">
          Login
        </v-btn>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
  export default {
    data() {
      return {
        email: "",
        password: "",
        showPassword: false,
        emailRules: [
          v => !!v || "Required",
          v => /.+@.+\..+/.test(v) || "E-mail must be valid"
        ],
        passwordRules: {
          required: value => !!value || "Required.",
          min: v => (v && v.length >= 8) || "Min 8 characters"
        }
      };
    },
    methods: {
      submitLogin() {
        if (! this.email || ! this.password) return;
        this.$emit('displayLoginWindow', false);
        console.log(this.email);
        console.log(this.password);
      },
    },
  }
</script>
