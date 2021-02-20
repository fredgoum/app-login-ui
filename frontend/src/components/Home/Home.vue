<template>
  <div>
    <!-- Navigation -->
    <navigation></navigation>
    <!-- Home Content -->
    <home-content></home-content>
  </div>
</template>

<script>
  import Navigation from '../Navigation/Navigation';
  import HomeContent from './HomeContent';

  export default {
    components: {
      Navigation,
      HomeContent,
    }
  }
</script>
