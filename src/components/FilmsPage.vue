<template>
  <div>
    <h1 class="movie-titolo">MOVIES</h1>
    <div class="container">
      <CardPage
      v-for="film in arrFilms"
      :key="film.id"
      :imgUrl="`${thumbLink}${film.poster_path}`"
      :title1="film.title"
      :title2="film.original_title"
      :language="film.original_language"
      :rating="film.vote_average"
      :overview="film.overview"/>
    </div>
  </div>
</template>

<script>
import CardPage from '@/components/CardPage.vue';

export default {
  name: 'FilmsPage',
  components: {
    CardPage,
  },

  props: {
    arrFilms: Array,
  },

  data() {
    return {
      thumbLink: 'https://image.tmdb.org/t/p/original',
    };
  },
};
</script>

<style lang="scss">
.movie-titolo {
  font-size: 100px;
  color: white;
  border: 15px solid red;
  text-align: center;
  background-color: black;
}
.container {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}
</style>
