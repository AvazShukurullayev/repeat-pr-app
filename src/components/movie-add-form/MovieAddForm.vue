<template>
  <MyBox class="movie-add-form">
    <h2 class="movie-add-form__title">Kino qo'shish</h2>
    <form @onSubmit="onSubmit" class="d-flex">
      <input
        type="text"
        class="form-control"
        placeholder="Kinoni nomini kiriting"
      />
      <input
        type="number"
        class="form-control"
        placeholder="Kinoni necha marotaba ko'rilgan"
      />
      <button class="btn btn-outline-dark" type="submit">Qo'shish</button>
    </form>
  </MyBox>
</template>

<script>
import MyBox from "@/components/ui-components/MyBox.vue";
export default {
  name: "MovieAddForm",
  props: [],
  components: { MyBox },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style></style>
