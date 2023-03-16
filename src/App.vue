<template>
  <FirstTask>
  </FirstTask>
</template>

<script>
import FirstTask from "@/components/FirstTask.vue";

export default {
  components: {FirstTask}
}

</script>

<style>
@font-face {
  font-family: GheaGrapalat, sans-serif;
  src: url("@/assets/fonts/gheagrapalat.otf") format("opentype");
  font-weight: normal;
}

* {
  padding: 0;
  margin: 0;
  border: 0;
  box-sizing: border-box;
  color: #EEEBE6;
  text-transform: uppercase;
}

body {
  background-color: #21354B;
  font-family: GheaGrapalat, sans-serif;
}

</style>
