<script setup>
import TermContainer from './TermContainer.vue';
import TermIcon from "../src/components/TermIcon.vue"

</script>


<template>
    <div class="backgroundImage">
        <TermContainer/>
        <TermIcon/>
</div>
</template>

<style scoped>

.backgroundImage {
  background-image: url("../src/assets/bg-ground.jpg");
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  position: relative;
  min-width: 320px;
  min-height: 100vh;
  background-size: cover;
  color: black;
  overflow: hidden;
}


</style>