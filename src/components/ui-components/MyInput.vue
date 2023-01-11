<template>
  <input type="text" class="form-control" @input="$emit('input', $event)" />
</template>

<script>
export default {
  name: "MyInput",
};
</script>

<style></style>
