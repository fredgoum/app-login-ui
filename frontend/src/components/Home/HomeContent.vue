<template>
  <div>
    <!-- Login Window -->
    <login-window></login-window>

    <!-- Home Content -->
    <div>
      <div class="text-center pa-5">
        Bienvenue sur Ikena <br>
        Votre plate-forme de communication collaborative
      </div>
    </div>
  </div>
</template>

<script>
  import LoginWindow from '../User/LoginWindow';
  
  export default {
    components: { 
      LoginWindow,
    },
  };
</script>
