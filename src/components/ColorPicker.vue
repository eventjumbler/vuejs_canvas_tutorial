<template>
  <div>
    <Pixel color_num="0" :is_selected="selected_color == '0' ? true : false" :is_picker="true"/>
    <Pixel color_num="1" :is_selected="selected_color == '1' ? true : false" :is_picker="true"/>
    <Pixel color_num="2" :is_selected="selected_color == '2' ? true : false" :is_picker="true"/>
    <Pixel color_num="3"  :is_selected="selected_color == '3' ? true : false" :is_picker="true"/>
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
