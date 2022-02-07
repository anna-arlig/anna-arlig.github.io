<template>
  <div class="grid" v-bind:style="stylesObject">
    <PixelCell
      v-for="pixel in numberOfPixels"
      v-bind:key="pixel"
      :activeColor="activeColor"
    />
  </div>
</template>

<script>
import PixelCell from "./PixelCell.vue";

export default {
  components: { PixelCell },
  props: ["rows", "columns", "activeColor"],
  computed: {
    stylesObject() {
      return {
        backgroundColor: "darkgrey",
        border: "2px solid white",
        display: "grid",
        gap: "0.2mm",
        gridTemplateRows: `repeat(${this.rows}, 1fr)`,
        gridTemplateColumns: `repeat(${this.columns}, 1fr)`,
        maxWidth: "400px",
        minHeight: "400px",
      };
    },
  },
  data() {
    return {
      numberOfPixels: this.columns * this.rows,
    };
  },
};
</script>

<style scoped></style>
