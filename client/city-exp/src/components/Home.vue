<template>
  <div class="home">
    <Login />
  </div>
</template>

<script>

import Login from './Login.vue';

export default {
  name: 'home',
  components: {
    Login,
  },
  data() {
    return {
      info: null,
      errored: false,
      loading: true,
    };
  },
  methods: {
  },
};
</script>

<style>

</style>
