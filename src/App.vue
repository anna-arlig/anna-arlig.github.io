<template>
  <div class="wrapper">
    <header><h1>Pixel Editor</h1></header>
    <p v-if="gridSet">
      Check out
      <a
        href="https://www.color-hex.com/"
        target="_blank"
        rel="noopener noreferrer"
        >Color-hex</a
      >
      for some custom color codes!
    </p>

    <SetGrid
      v-if="!gridSet"
      :gridSet="gridSet"
      @rowInput="setRows"
      @columnInput="setColumns"
      @click="gridSet = !gridSet"
    />
    <ColorPicker v-if="gridSet" @changeActiveColor="changeActiveColor" />
    <PixelGrid
      v-if="gridSet"
      :rows="rows"
      :columns="columns"
      :activeColor="activeColor"
    />
  </div>
</template>

<script>
import SetGrid from "./components/SetGrid.vue";
import ColorPicker from "./components/ColorPicker.vue";
import PixelGrid from "./components/PixelGrid.vue";

export default {
  components: { SetGrid, ColorPicker, PixelGrid },
  data() {
    return {
      activeColor: "",
      rows: null,
      columns: null,
      gridSet: false,
    };
  },
  methods: {
    changeActiveColor(color) {
      this.activeColor = color;
    },

    setRows(rowInputData) {
      return (this.rows = rowInputData);
    },
    setColumns(columnInputData) {
      return (this.columns = columnInputData);
    },
  },
};
</script>

<style>
* {
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}
html,
body {
  background-color: black;
  display: flex;
  justify-content: center;
}

h1 {
  color: white;
  text-align: center;
}
p {
  color: white;
  text-align: center;
}
</style>
