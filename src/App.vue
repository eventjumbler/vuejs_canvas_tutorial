<template>
  <div id="app">
    <ColorPicker :selected_color="selected_color"/>
    <Canvas :pixels="pixels"/>
  </div>
</template>


<script>
import Vue from 'vue'
import Canvas from "./components/Canvas";
import ColorPicker from "./components/ColorPicker";

const defaultColor = 'white';

function createPixels(){
  var arr = Array(30*30);
  for(var i=0; i < arr.length; i++){
      arr[i] = defaultColor;
  }
  return arr;
}

export default {
  name: "App",
  components: {
    Canvas,
    ColorPicker
  },
  data: function() {
    return {
      selected_color: "white",
      pixels: createPixels(),
    };
  },
  methods: {
    setPixel(index){
        Vue.set(this.pixels, index, this.selected_color);  // cannot set array val directly
    }
  },
  mounted() {
    this.$root.$on("updatecolor", color => {
      this.selected_color = color;
    });

    this.$root.$on('pixelclicked', this.setPixel);
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #333;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
</style>
