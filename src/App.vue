<template>
  <div id="app">
    <div class="container font-monospace">
      <div class="content">
        <AppInfo />
        <div class="search-panel">
          <SearchInput />
          <FilterButtons />
        </div>
        <MovieList />
        <MovieAddForm />
      </div>
    </div>
  </div>
</template>

<script>
import AppInfo from "@/components/app-info/AppInfo.vue";
import SearchInput from "@/components/search-input/SearchInput.vue";
import FilterButtons from "@/components/filter-buttons/FilterButtons.vue";
import MovieList from "@/components/movie-list/MovieList.vue";
import MovieAddForm from "@/components/movie-add-form/MovieAddForm.vue"
export default {
  name: "App",
  components: { AppInfo, SearchInput, FilterButtons, MovieList,MovieAddForm },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss">
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
