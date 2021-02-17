<template>
  <v-app>
    <v-main>
      <!-- Home -->
      <home></home>
    </v-main>
  </v-app>
</template>

<script>
  import Home from './components/Home/Home';

  export default {
    components: {
      Home,
    },
  };
</script>
