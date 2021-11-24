<template>
  <div id="element" :style="elementStyle">
    <div class="number">
      <span>{{ data.atomicNumber }}</span>
      <span>{{ parseFloat(data.atomicMass).toFixed(1) }}</span>
    </div>
    <div class="symbol">{{ data.symbol }}</div>
    <div class="name">{{ data.name }}</div>
  </div>
</template>

<script>

export default {
  name: "Element",
  props: {
    data: Object
  },
  data() {
    return {
      elementStyle: {
        backgroundColor: "#" + this.data.cpkHexColor
      }
    };
  }
};

</script>

<style>
#element {
  width: 50px;
  height: 50px;
  border: 2px black solid;
}

.number {
  display: flex;
  justify-content: space-between;
  font-size: 7px;
}

.symbol {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 17px;
}

.name {
  margin-top: 7px;
  font-size: 7px;
}
</style>
