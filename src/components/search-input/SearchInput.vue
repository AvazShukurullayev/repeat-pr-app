<template>
  <input
    type="text"
    class="form-control search-input mb-3"
    placeholder="Kino qidirish..."
    @input="$emit('onSearch', $event.target.value)"
  />
</template>

<script>
export default {
  name: "SearchInput",
  props: [],
  components: {},
  data() {
    return {};
  },
  methods: {},
};
</script>

<style></style>
