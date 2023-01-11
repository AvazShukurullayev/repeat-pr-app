<template>
  <MyBox class="app-info">
    <MyParag class="fs-3">Barcha kinolar soni: {{ moviesLength }}</MyParag>
    <MyParag class="fs-4">Favourite kinolar sonni: {{ favouriteMoviesLength }}</MyParag>
    <MyParag class="fs-4">Liked kinolar sonni: {{ likedMoviesLength }}</MyParag>
  </MyBox>
</template>

<script>
import MyBox from "@/components/ui-components/MyBox.vue";
import MyParag from "@/components/ui-components/MyParag.vue";
export default {
  name: "AppInfo",
  props: ["moviesLength", "favouriteMoviesLength", "likedMoviesLength"],
  components: { MyParag ,MyBox},
  data() {
    return {};
  },
  methods: {},
};
</script>

<style></style>
