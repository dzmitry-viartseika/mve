<template>
    <div class="main">
      <div class="header">
        <div class="header-row">
          <div class="header-row__logo">
            <router-link class="header-row__logo-link" to="/">Movie Catalog</router-link>
          </div>
          <div class="header-row__search">
            <input class="search__input" placeholder="Search by Title" type="search" v-model="searching">
          </div>
          <div class="header-row__user">
            {{searching}}
            <User></User>
          </div>
        </div>
      </div>
      <Movies :filtered="filtered" :searching="searching"></Movies>
      <Pagination></Pagination>
    </div>
</template>

<script>

import axios from 'axios';
import Movies from '../components/Movies.vue';
import User from '../components/User.vue';
import Pagination from '../components/Pagination.vue';

export default {
  name: 'Home',
  components: {
    Movies,
    User,
    Pagination
  },
  data() {
    return {
      info: '',
      searching: ''
    }
  },
  computed: {
    filtered() {
      return this.info;
    },
  },
  beforeMount() {
    axios
      .get('https://www.omdbapi.com/?i=tt3896198&apikey=8523cbb8&s=Batman&page=2')
      .then((response) => {
        this.info = response.data.Search;
      })
      .catch(err => console.log(err));
  },
};
</script>

<style scoped lang="scss">
  .search {
    &__input {
      width: 780px;
      height: 30px;
      border: none;
      padding-left: 10px;
      font-size: 18px;
      @media screen and (max-width: 800px) {
        & {
          max-width: 500px;
        }
      }
      @media screen and (max-width: 800px) {
        & {
          max-width: 500px;
        }
      }
      @media screen and (max-width: 510px) {
        & {
          max-width: 300px;
        }
      }
    }
  }
</style>
