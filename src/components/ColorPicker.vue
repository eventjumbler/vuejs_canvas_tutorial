<template>
  <div>
    <Pixel color="white" :is_selected="selected_color == 'white' ? true : false" :is_picker="true"/>
    <Pixel color="lightblue" :is_selected="selected_color == 'lightblue' ? true : false" :is_picker="true"/>
    <Pixel color="blue" :is_selected="selected_color == 'blue' ? true : false" :is_picker="true"/>
    <Pixel color="darkblue" :is_selected="selected_color == 'darkblue' ? true : false" :is_picker="true"/>
  </div>
</template>


<script>
import Pixel from "./Pixel";

export default {
  name: "ColorPicker",
  components: {
    Pixel
  },
  props: ["selected_color"]
};
</script>
