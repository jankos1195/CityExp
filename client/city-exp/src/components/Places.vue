<template>
  <div class="container">
    <form>
      <div class="form-group">
        <label for="city">City</label>
        <input type="text" v-model="city">
      </div>
      <div class="form-group">
        <label for="city">Amenity</label>
        <input type="text" v-model="amenity">
      </div>
    </form>
    <div class="form-group">
      <button v-on:click="handleSearch" type="buton" class="btn btn-success">Search</button>
    </div>
    <ul>
      <li v-for="d in data"> {{ d.name }}</li>
    </ul>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  name: 'places',
  components: {
  },
  data() {
    return {
      city: '',
      amenity: '',
      data: null,
    };
  },
  methods: {
    handleSearch() {
      const postData = {
        city: this.city,
        amenity: this.amenity,
      };

      const postConfig = {
        headers: {
          'Content-Type': 'application/json;charset=UTF-8',
        },
      };

      axios
        .post('http://192.168.1.132:5000/api/register', postData, postConfig)
        .then((response) => {
          this.data = response.data;
          console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};

</script>

<style>
</style>
