<template>
  <div class="home">
    <h1>Bienvenue sur CaCaoCritics</h1>
    <img alt="Vue logo" src="../assets/logo.png" />
    <br />
    <input type="text" v-model="moviename" placeholder="enter a movie name"/>
    <div class="film-name">Le film est : {{ moviename }}</div>
    <li v-for="movie in movies" :key="movie.id">
    <p>
      {{ movie.title }} 
    </p>
    <p>
      <img :src= "'https://image.tmdb.org/t/p/original/' + movie.poster_path" withd="100" height="300" />
    </p>
    </li>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Home",
  data: function () {
    return {
      moviename: "",
      movies: [],
      moviesLoadingError: "",
    };
  },
  methods: {
    fetchMovies: function () {
      axios
        .get(
          `https://api.themoviedb.org/3/movie/popular?api_key=522d421671cf75c2cba341597d86403a`
        )
        .then((response) => {
          this.movies = response.data.results;
        })
        .catch((error) => {
          this.moviesLoadingError = "An error occured while fetching movies.";
          console.error(error);
        });
    },
  },
  created() {
    this.fetchMovies();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home {
  text-align: center;
}

h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #FF68AD;
}
</style>
