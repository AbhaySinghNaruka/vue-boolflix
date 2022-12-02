<template>
  <div>
    <h1 class="serie-titolo">SERIE TV</h1>
    <div class="container">
      <CardPage
      v-for="serie in arrSeries"
      :key="serie.id"
      :imgUrl="`${thumbLink}${serie.poster_path}`"
      :title1="serie.name"
      :title2="serie.original_name"
      :language="serie.original_language"
      :rating="serie.vote_average"
      :overview="serie.overview"/>
    </div>
  </div>
</template>

<script>
import CardPage from '@/components/CardPage.vue';

export default {
  name: 'SeriesPage',
  components: {
    CardPage,
  },

  props: {
    arrSeries: Array,
  },

  data() {
    return {
      thumbLink: 'https://image.tmdb.org/t/p/original',
    };
  },
};
</script>

<style lang="scss">
.serie-titolo {
  font-size: 100px;
  color: white;
  border: 15px solid red;
background-color: black;
  text-align: center;
}
.container {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}
</style>
