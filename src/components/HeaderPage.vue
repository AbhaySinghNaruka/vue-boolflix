<template>
  <header class="header">
    <div class="logo">
      <h1>BOOLFLIX</h1>
    </div>
    <form @submit.prevent="$emit('search', query)">
      <label for="search">
        <input
        v-model="query"
        type="text"
        placeholder="Cerca un film o una serie TV">
      </label>
      <button>CERCA</button>
    </form>
  </header>
</template>

<script>
export default {
  name: 'HeaderPage',
  data() {
    return {
      query: '',
    };
  },
};
</script>

<style lang="scss">
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 100px;
  background-color: black;
    h1 {
      color: red;
      margin-left: 25px;
      font-size: 50px;
    }

    form {
      margin-right: 50px;

      button {
        width: 100px;
        height: 35px;
        background-color: blue;
        color: white;
      }
    }

    input {
      width: 200px;
      height: 35px;
    }
}
</style>
