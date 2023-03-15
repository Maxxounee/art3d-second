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
  font-family: gheagrapalat;
  src: url("@/assets/fonts/gheagrapalat.otf") format("otf");
  font-weight: normal;
}

@font-face {
  font-family: gheamariam;
  src: url("@/assets/fonts/gheamariam.otf") format("otf");
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
  font-family: gheagrapalat, Verdana, sans-serif;
}

</style>
