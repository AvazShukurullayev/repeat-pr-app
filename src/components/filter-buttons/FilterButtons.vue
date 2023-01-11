<template>
  <div class="btn-group">
    <MyButton
      v-for="filterBtn in filterButtons"
      @click="filterButton(filterBtn.btnValue)"
      :key="filterBtn.btnTitle"
      :class="[
        filterBtn.btnValue == filterButtonValue
          ? 'btn-dark'
          : 'btn-outline-dark',
      ]"
    >
      {{ filterBtn.btnTitle }}
    </MyButton>
  </div>
</template>

<script>
import MyButton from "@/components/ui-components/MyButton.vue";
export default {
  name: "FilterButtons",
  props: [],
  components: { MyButton },
  data() {
    return {
      filterButtons: [
        {
          btnTitle: "Barcha kinolar",
          btnValue: "all",
        },
        {
          btnTitle: "Mashxur kinolar",
          btnValue: "popular",
        },
        {
          btnTitle: "Eng ko'p ko'rilgan kinolar",
          btnValue: "mostViewers",
        },
      ],
      filterButtonValue: "all",
    };
  },
  methods: {
    filterButton(par) {
      this.filterButtonValue = par;
      this.$emit("onFilterButton", this.filterButtonValue);
    },
  },
};
</script>

<style></style>
