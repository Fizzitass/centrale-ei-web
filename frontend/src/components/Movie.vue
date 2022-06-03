<template>
  <table>
    <thead>
      <th>Titre</th>
      <th>Date de sortie</th>
      <th>Image</th>
    </thead>
    <tbody>
      <tr v-for="movie in movies" :key="movie.id">
        <td>{{ movie.title }}</td>
        <td>{{ movie.release_date }}</td>
        <td> <img :src= "'https://image.tmdb.org/t/p/original/' + movie.poster_path" /> </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    movies: Array,
  },
};
</script>

<style scoped>
</style>
