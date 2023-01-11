<template>
  <div id="app">
    <div class="container font-monospace">
      <div class="content">
        <AppInfo
          :moviesLength="movies.length"
          :favouriteMoviesLength="movies.filter((c) => c.favourite).length"
          :likedMoviesLength="movies.filter((c) => c.like).length"
        />
        <MyBox class="search-panel">
          <SearchInput />
          <FilterButtons />
        </MyBox>
        <MovieList  />
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
import MovieAddForm from "@/components/movie-add-form/MovieAddForm.vue";
import MyBox from "@/components/ui-components/MyBox.vue";
export default {
  name: "App",
  components: {
    AppInfo,
    SearchInput,
    FilterButtons,
    MovieList,
    MovieAddForm,
    MyBox,
  },
  data() {
    return {
      movies: [
        {
          title: "Omar",
          viewers: 811,
          favourite: false,
          like: false,
          id: 1,
        },
        {
          title: "Empire of Osman",
          viewers: 1411,
          favourite: false,
          like: false,
          id: 2,
        },
        {
          title: "Ertugrul",
          viewers: 411,
          favourite: false,
          like: false,
          id: 3,
        },
        {
          title: "Empire of Rome",
          viewers: 711,
          favourite: false,
          like: false,
          id: 4,
        },
        {
          title: "Abdulhamid II",
          viewers: 1081,
          favourite: false,
          like: false,
          id: 5,
        },
        {
          title: "Murad IV. Bagdag Fatihi",
          viewers: 984,
          favourite: false,
          like: false,
          id: 6,
        },
      ],
    };
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
