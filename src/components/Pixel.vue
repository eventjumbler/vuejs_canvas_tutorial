
<template>
  <div @click="handleClick" :class="['pixel', color, is_selected ? 'selected': '']"></div>
</template>

<script>
const colors = ['white', 'lightblue', 'blue', 'darkblue'];

export default {
  name: "Pixel",
  props: {
    color_num: Number,
    is_selected: Boolean,
    is_picker: Boolean,
    index: Number
  },
  methods: {
    handleClick: function() {
      if (this.is_picker) {
        this.$root.$emit("updatecolor", this.color_num);
        return;
      }
      this.$root.$emit("pixelclicked", this.index);
    }
  },
  computed: {
    color: function(){
      return colors[this.color_num];
    }
  }
};
</script>


<style scoped>
.pixel {
  border: 1px solid lightgray;
  width: 30px;
  height: 30px;
  box-sizing: border-box;
}

.white {
  background-color: white;
}
.lightblue {
  background-color: rgb(0, 188, 212);
}
.blue {
  background-color: rgb(3, 169, 244);
}
.darkblue {
  background-color: rgb(33, 150, 243);
}

.pixel.selected {
  border: 4px solid yellow;
}
</style>
