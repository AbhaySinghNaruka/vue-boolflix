<template>
  <div class="card">
      <img :src="imgUrl" :alt="title2">
    <ul class="infos">
      <li class="title">
        TITOLO: <span class="contenuto">{{ title1 }}</span>
      </li>
      <li class="original-title">
        Titolo Originale: <span class="contenuto">{{title2}}</span>
      </li>
      <li class="language">
        Lingua: <span class="contenuto">{{ language }}</span>
      </li>
      <li class="rating">
        Voto: <span class="contenuto">{{ rating }}</span>
      </li>
      <li class="overview">
        Overview: <span class="contenuto">{{ overview }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'CardPage',
  props: {
    imgUrl: String,
    title1: String,
    title2: String,
    language: String,
    rating: Number,
    overview: String,
  },
};
</script>

<style lang="scss">
.card {
  background-color: rgb(32, 32, 32);
  border: 5px solid rgb(255, 0, 0);
  position: relative;
  width: 325px;
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .infos {
    height: 100%;
    color: rgb(153, 153, 153);
    font-size: 20px;
    font-weight: bolder;
    width: 100%;
    padding: 15px;
    position: absolute;
    overflow-y: auto;
    display: none;

    li{
      margin: 15px 0;
    }
    .contenuto {
    font-size: 20px;
    color: white;
    };
  }
}

.card:hover img{
display: none;
}

.card:hover .infos {
  display: block;
}
</style>
