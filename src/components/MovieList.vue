<template>
  <div id="movie-container">
    Movie List
    <Movie v-for="movie in movies" :key="movie.id" :movie="movie" />
  </div>
</template>

<script>
import Movie from "./Movie";

export default {
  components: {
    Movie,
  },
  data() {
    return {
      movies: [
        { id: 1, name: "movie 1" },
        { id: 2, name: "movie 2" },
        { id: 3, name: "movie 3" },
        { id: 4, name: "movie 4" },
      ],
    };
  },
  computed: {
    movies() {
      return this.$store.getters.getMovies;
    },
  },
  //   created() {
  //     this.movies = this.$store.getters.getMovies;
  //   },
};
</script>

<style lang="scss" scoped>
#movie-container {
  padding-top: 1rem;
  display: flex;
  flex-wrap: wrap;
  flex-grow: 2;
  justify-content: center;
}
</style>
