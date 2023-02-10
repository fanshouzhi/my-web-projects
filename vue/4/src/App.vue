<script setup lang="ts">
import hswInput from "./components/hsw-input.vue";
</script>

<template>
  <hswInput />
</template>

<style lang="less">
@import "./style/variable.less";
body {
  margin: 0;
  padding: 0;
  background: linear-gradient(135deg,@body_bg_color_1 10%,@body_bg_color_2 90%);
  .app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
}
</style>