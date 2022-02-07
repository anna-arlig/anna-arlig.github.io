<template>
  <div class="set-grid-container">
    <h2>Ange dimensioner</h2>
    <input
      type="text"
      placeholder="Rader"
      v-model="rowInputData"
      @input="$emit('rowInput', rowInputData)"
      @keyup.enter="$emit('click')"
    />
    <input
      type="text"
      placeholder="Kolumner"
      v-model="columnInputData"
      @input="$emit('columnInput', columnInputData)"
      @keyup.enter="$emit('click')"
    />
    <button class="grid-btn" @click="$emit('click')">Börja rita</button>
  </div>
</template>

<script>
export default {
  props: ["gridSet"],
  data() {
    return {
      rowInputData: null,
      columnInputData: null,
    };
  },
};
</script>

<style scoped>
h2 {
  color: white;
  text-align: center;
  margin-top: 50px;
  margin-bottom: 20px;
  font-size: 20px;
}
.set-grid-container {
  display: flex;
  flex-direction: column;
}
input {
  margin: 5px;
  color: white;
  background-color: black;
  border: solid rgb(102, 39, 102);
  border-radius: 5px;
  font-size: 15px;
  height: 25px;
}
.grid-btn {
  border: solid rgb(102, 39, 102);
  font-size: 15px;
  border-radius: 40px;
  color: white;
  background: rgb(186, 49, 130);
  background: linear-gradient(
    90deg,
    rgba(186, 49, 130, 1) 0%,
    rgba(39, 68, 140, 1) 100%
  );
  height: 30px;
  margin-top: 20px;
}
</style>
