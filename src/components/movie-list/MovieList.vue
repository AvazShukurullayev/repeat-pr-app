<template>
  <ul class="list-group">
    <MovieListItem
      v-for="movie in movies"
      :movie="movie"
      :key="movie.id"
      @onLike="$emit('onLike', $event)"
      @onFavourite="$emit('onFavourite', $event)"
      @onRemove="$emit('onRemove', $event)"
    />
  </ul>
</template>

<script>
import MovieListItem from "@/components/movie-list-item/MovieListItem.vue";
export default {
  name: "MovieList",
  props: ["movies"],
  components: { MovieListItem },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style>
.list-group {
  margin: 1.5rem 0;
  padding: 1rem;
  border-radius: 6px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
  background-color: #fcf8f4;
}
</style>
