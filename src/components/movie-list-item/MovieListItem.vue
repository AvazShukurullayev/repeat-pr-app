<template>
  <li
    class="list-group-item d-flex align-items-center justify-content-between"
    :class="{ favourite: movie.favourite, like: movie.like }"
  >
    <span class="list-group-item__label" @click="$emit('onLike', movie.id)">
      {{ movie.title }}
    </span>
    <div class="list-group-item__content d-flex align-items-center">
      <input
        type="number"
        class="form-control list-group-item__input"
        :value="movie.viewers"
      />
      <button class="btn-cookie btn-sm" @click="$emit('onFavourite', movie.id)">
        <i class="fas fa-cookie"></i>
      </button>
      <button class="btn-trash btn-sm" @click="$emit('onRemove', movie.id)">
        <i class="fas fa-trash"></i>
      </button>
      <i class="fas fa-star"></i>
    </div>
  </li>
</template>

<script>
export default {
  name: "MovieListItem",
  props: ["movie"],
  components: {},
  data() {
    return {};
  },
  methods: {},
};
</script>

<style>
.list-group-item__label {
  max-width: 550px;
  width: 100%;
  line-height: 35px;
  font-size: 20px;
  cursor: pointer;
}
.list-group-item__input {
  text-align: center;
  font-size: 18px;
}
.btn-cookie,
.btn-trash {
  margin: 3px 5px;
  width: 35px;
  height: 35px;
  border: none;
  outline: none;
  transition: all 0.3s;
}
.btn-cookie {
  color: gold;
}
.btn-trash {
  color: red;
}
.btn-cookie:hover,
.btn-trash:hover {
  background-color: rgb(184, 184, 184);
}
.fa-star {
  width: 35px;
  opacity: 0;
  color: gold;
  transform: translateX(25px);
  transition: all 0.3s;
}
.list-group-item.like .fa-star {
  opacity: 1;
  transform: translateX(0);
}
.list-group-item.favourite .list-group-item__label,
.list-group-item.favourite .list-group-item__input {
  color: gold;
}
</style>
