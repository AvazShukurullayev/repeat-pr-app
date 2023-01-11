<template>
  <div id="app">
    <div class="container font-monospace">
      <div class="content">
        <AppInfo
          :moviesLength="movies.length"
          :favouriteMoviesLength="
            movies.filter((element) => element.favourite).length
          "
          :likedMoviesLength="movies.filter((element) => element.like).length"
        />
        <MyBox class="search-panel">
          <SearchInput @onSearch="onSearch" />
          <FilterButtons @onFilterButton="onFilterButton" />
        </MyBox>
        <MovieList
          :movies="
            onFilterButtonMovies(
              onSearchMovies(movies, filterWord),
              filterButton
            )
          "
          @onLike="onLikeApp"
          @onFavourite="onFavouriteApp"
          @onRemove="onRemoveApp"
        />
        <MovieAddForm @onSubmit="onSubmit" />
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
      filterWord: "",
      filterButton: "all",
    };
  },
  methods: {
    onFilterButtonMovies(arr, filterButton) {
      switch (filterButton) {
        case "popular":
          return arr.filter((element) => element.favourite);
        case "mostViewers":
          return arr.filter((element) => element.viewers > 500);
        default:
          return arr;
      }
    },
    onSearchMovies(arr, filterWord) {
      if (filterWord.length == 0) {
        return arr;
      }
      return arr.filter((element) =>
        element.title.toLowerCase().includes(filterWord.toLowerCase())
      );
    },
    onLikeApp(id) {
      this.movies = this.movies.map((element) => {
        if (element.id === id) {
          element.like = !element.like;
        }
        return element;
      });
    },
    onFavouriteApp(id) {
      this.movies = this.movies.map((element) => {
        if (element.id === id) {
          element.favourite = !element.favourite;
        }
        return element;
      });
    },
    onRemoveApp(id) {
      this.movies = this.movies.filter((element) => element.id !== id);
    },
    onSearch(par) {
      this.filterWord = par;
    },
    onFilterButton(par) {
      this.filterButton = par;
    },
    onSubmit(param) {
      this.movies.push(param);
    },
  },
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
