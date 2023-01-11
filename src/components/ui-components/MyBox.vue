<template>
  <div class="my-box">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "MyBox",
};
</script>

<style>
.my-box {
  margin: 1.5rem 0;
  padding: 1rem;
  border-radius: 6px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
  background-color: #fcf8f4;
}
</style>
