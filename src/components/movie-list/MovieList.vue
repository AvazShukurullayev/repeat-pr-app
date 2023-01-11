<template>
  <ul class="list-group">
    <MovieListItem />
  </ul>
</template>

<script>
import MovieListItem from "@/components/movie-list-item/MovieListItem.vue";
export default {
  name: "MovieList",
  props: [],
  components: { MovieListItem },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style></style>
