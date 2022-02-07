<template>
  <div class="picker">
    <div
      class="color-picker"
      v-for="(color, index) in colors"
      :key="color"
      :style="{ backgroundColor: colors[index] }"
      @click="chooseColor(color)"
      :activeColor="activeColor"
    ></div>
    <div
      class="color-picker"
      :style="{ backgroundColor: customColor }"
      @click="setCustomColor(customColor)"
    ></div>
    <input
      @change="setCustomColor(customColor)"
      type="text"
      placeholder="Input custom color code"
      v-model="customColor"
    />
  </div>
</template>

<script>
export default {
  methods: {
    chooseColor(color) {
      this.activeColor = color;
      this.$emit("changeActiveColor", color);
    },
    setCustomColor(customColor) {
      this.$emit("changeActiveColor", customColor);
    },
  },
  data() {
    return {
      activeColor: "",
      customColor: "",
      colors: [
        "CornflowerBlue",
        "DarkOrange",
        "DeepPink",
        "DarkTurquoise",
        "Gold",
        "MediumSeaGreen",
        "PeachPuff",
        "DarkViolet",
        "White",
        "Azure",
        "Black",
      ],
    };
  },
};
</script>

<style scoped>
.picker {
  padding: 10px;
  max-width: 380px;
  background-color: white;
  border-radius: 5px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.color-picker {
  min-width: 20px;
  min-height: 20px;
  border-radius: 3px;
  margin: 5px;
  border: 1px solid black;
}

h1 {
  color: black;
}
</style>
