<template>
  <div
    class="cell"
    @click="changeColor"
    :style="{ backgroundColor: backgroundColor }"
  ></div>
</template>

<script>
export default {
  props: ["activeColor"],
  data() {
    return {
      backgroundColor: "black",
    };
  },
  methods: {
    changeColor() {
      this.backgroundColor = this.activeColor;
    },
  },
};
</script>

<style scoped>
.cell {
  color: white;
}
</style>
