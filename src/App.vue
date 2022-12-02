<template>
  <div>
    <HeaderPage @search="search"/>
    <MainPage class="main-page"
    :arrFilms="arrFilms"
    :arrSeries="arrSeries"
    />
  </div>
</template>

<script>
import axios from 'axios';
import HeaderPage from '@/components/HeaderPage.vue';
import MainPage from '@/components/MainPage.vue';

export default {
  name: 'App',
  components: {
    HeaderPage,
    MainPage,
  },

  data() {
    return {
      arrFilms: null,
      arrSeries: null,
      urlApiMovies: 'https://api.themoviedb.org/3/search/movie',
      urlApiSeries: 'https://api.themoviedb.org/3/search/tv',
      apiKey: '160e30b80c1e6ccd305435a3f159b22a',
      query: '',
      language: 'it-IT',
    };
  },

  methods: {
    search(data) {
      this.query = data;

      axios.get(this.urlApiMovies, {
        params: {
          api_key: this.apiKey,
          query: this.query,
          language: this.language,
        },
      })
        .then((axiosResult) => {
          this.arrFilms = axiosResult.data.results;
          console.log(this.arrFilms);
        });

      axios.get(this.urlApiSeries, {
        params: {
          api_key: this.apiKey,
          query: this.query,
          language: this.language,
        },
      })
        .then((axiosResult) => {
          this.arrSeries = axiosResult.data.results;
          console.log(this.arrSeries);
        });
    },
  },
};
</script>

<style lang="scss">
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  background-image: url('@/assets/Netflix-Background-prueba-1.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
}

.main-page {
    height: calc(100vh - 100px);
    overflow-y: scroll;
    overflow-x: hidden;
}

ul {
  list-style: none;
}
</style>
