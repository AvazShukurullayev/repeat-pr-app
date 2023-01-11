<template>
  <button class="btn" type="button" @click="$emit('click'), $event">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "MyButton",
};
</script>

<style></style>
