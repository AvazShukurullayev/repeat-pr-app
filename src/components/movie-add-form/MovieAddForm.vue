<template>
  <MyBox class="movie-add-form">
    <h2 class="movie-add-form__title">Kino qo'shish</h2>
    <form @submit.prevent="onSubmitForm" class="d-flex">
      <input
        type="text"
        class="form-control"
        placeholder="Kinoni nomini kiriting"
        v-model="form.title"
        required
      />
      <input
        type="number"
        class="form-control"
        placeholder="Kinoni necha marotaba ko'rilgan"
        v-model="form.viewers"
        required
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
    return {
      form: {},
    };
  },
  methods: {
    onSubmitForm() {
      const newMovieItem = {
        title: this.form.title,
        viewers: this.form.viewers,
        favourite: false,
        like: false,
        id: Date.now(),
      };
      this.$emit("onSubmit", newMovieItem);
      this.form = {};
    },
  },
};
</script>

<style></style>
