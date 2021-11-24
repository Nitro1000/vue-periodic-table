<template>
  <div id="table">
    <Element v-for="(element,index) in elements" :key="index" :data="element">
    </Element>
  </div>
</template>

<script>
import Element from "./Element.vue";

export default {
  name: "Table",
  components: {
    Element
  },

  data() {
    return {
      elements: null
    };
  },
  mounted() {
    fetch("data.json")
      .then(response => response.json())
      .then(data => { this.elements = JSON.parse(JSON.stringify(data, ["atomicNumber", "symbol", "name", "atomicMass", "cpkHexColor", "groupBlock"])); })
      .catch(error => console.log(error));
  },
};

</script>

<style>
#table {
  display: flex;
  flex-wrap: wrap;
}
</style>
