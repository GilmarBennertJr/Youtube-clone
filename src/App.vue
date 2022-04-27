<template>
    <router-view></router-view>
</template>

<script>

import { routes } from './routes';

export default {
  components: {
  },
  data() {
    return {
      routes
    }
  }
}
</script>

<style>
  body {
    font-family: sans-serif
  }
  
  .inline-flex {
    display: inline-flex;
  }

  .width50p {
    width: 50%;
  }

  .width100p {
    width: 100%;
  }
</style>
