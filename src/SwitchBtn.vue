<template>
  <div>
    <div id="on" @click="switched(true)" :class="{active: value}" class="m-mr10">On</div>
    <div id="off" @click="switched(false)" :class="{active: !value}">Off</div>
  </div>
</template>

<script>
export default {
  props: ["value"],
  methods: {
    switched(isOn) {
      this.$emit("input", isOn);
    }
  }
};
</script>

<style scoped>
#on,
#off {
  width: 40px;
  height: 20px;
  background-color: lightgray;
  padding: 2px;
  display: inline-block;
  margin: 10px -2px;
  box-sizing: content-box;
  cursor: pointer;
  text-align: center;
}

#on:hover,
#on.active {
  background-color: green;
}

#off:hover,
#off.active {
  background-color: red;
}
#on {
  margin-right: 10px;
}
</style>