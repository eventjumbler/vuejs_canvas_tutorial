<template>
  <div class="canvas">
    <Pixel :is_picker="false" v-for="(color, index) in pixels" :color="color" :key=index :index=index />
  </div>
</template>

<script>
import Pixel from "./Pixel";

export default {
  name: "Canvas",
  components: {
    Pixel
  },
  props: ["pixels"]
};
</script>

<style scoped>
.canvas {
  display: flex;
  flex-wrap: wrap;
  max-width: 900px;
}
</style>
