<template>
  <v-card class="pa-4">
    <v-row>
      <!-- Firstname -->
      <v-col cols="12" sm="6" md="6">
        <v-text-field v-model="firstName" :rules="[rules.required]" label="First Name" maxlength="20" required></v-text-field>
      </v-col>
      <!-- Lastname -->
      <v-col cols="12" sm="6" md="6">
        <v-text-field v-model="lastName" :rules="[rules.required]" label="Last Name" maxlength="20" required></v-text-field>
      </v-col>
      <!-- Email -->
      <v-col cols="12">
        <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>
      </v-col>
      <!-- Password -->
      <v-col cols="12">
        <v-text-field v-model="password" :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                      :rules="[rules.required, rules.min]" type="password" label="Password"
                      hint="At least 8 characters" counter
                      @click:append="showPassword = !showPassword">
          </v-text-field>
      </v-col>
      <!-- Confirm Password -->
      <v-col cols="12">
        <v-text-field block v-model="verify" :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                      :rules="[rules.required, passwordMatch]" :type="showPassword ? 'text' : 'password'"
                      name="input-10-1" label="Confirm Password" counter
                      @click:append="showPassword = !showPassword">
        </v-text-field>
      </v-col>
      <v-spacer></v-spacer>
      <!-- Submit -->
      <v-col class="d-flex justify-end pr-8" cols="12">
        <v-btn class="text-capitalize" large rounded color="success" @click="submitRegister">
          Register
        </v-btn>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
  export default {
    data() {
      return {        
        firstName: "",
        lastName: "",
        email: "",
        password: "",
        verify: "",
        showPassword: false,
        emailRules: [
          v => !!v || "Required",
          v => /.+@.+\..+/.test(v) || "E-mail must be valid"
        ],
        rules: {
          required: value => !!value || "Required.",
          min: v => (v && v.length >= 8) || "Min 8 characters"
        }
      };
    },
    computed: {
      passwordMatch() {
        return () => this.password === this.verify || "Password must match";
      }
    },
    methods: {
      submitRegister() {
        if (! this.firstName || this.lastName || this.email || this.password) return;
        this.$emit('displayLoginWindow', false);
        console.log(this.firstName);
        console.log(this.lastName);
        console.log(this.email);
        console.log(this.password);
      },
    },
  }
</script>
