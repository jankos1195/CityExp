<template>
  <div class="container">
    <h2>Login</h2>
    <form>
      <div class="form-group">
        <label for="username">Username</label>
        <input type="text" v-model="username">
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <input type="text" v-model="password">
      </div>
    </form>
    <div class="form-group">
      <button v-on:click="handleLogin" type="buton" class="btn btn-primary">Login</button>
    </div>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  name: 'login',
  data() {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    handleLogin() {
      const postData = {
        username: this.username,
        password: this.password,
      };

      const postConfig = {
        headers: {
          'Content-Type': 'application/json;charset=UTF-8',
        },
      };

      axios
        .post('http://192.168.1.132:5000/auth/register', postData, postConfig)
        .then((response) => {
          console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });

      this.username = '';
      this.password = '';
    },
  },
};

</script>

<style>
</style>
