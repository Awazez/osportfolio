<script setup>
import terminal from './components/terminal.vue';
import popUp from './components/popUp.vue';

defineProps({
  greetingMessage: Function
})

function callback() {
  console.log("Hello, world!")
}

</script>
<template>
  <div class="backgroundimage">
    <terminal @some-event="callback"/>
    <popUp/>
  </div>

</template>


<style scoped>
.backgroundimage {
  background-image: url('./assets/bg-ground.jpg');
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  position: relative;
  min-width: 320px;
  min-height: 100vh;
  background-size: cover;
  color: black;
  overflow: hidden;
}

button {
  width: 200px;
  height: 200px;
  background-color: black;
  color: white;
}

img {
  width: 60px;
  height: 60px;
  
}

.container {
    margin-left: 15px;
    margin-top: 15px;
}

.container-title {
    color:white;
    margin-left: -2px;
    margin-top: 30px;
}


    .box {
      margin-top: -200px;

    }

    .upper-box {
      width: 640px;
      height: 35px;
      border-top-left-radius:     10px;
      border-top-right-radius:    10px;
      color:white;
      border-bottom: 1px solid black;
      background-color: #473a36;
    }
    
    .inner-box {
      width: 640px;
      height: 275px;
      padding: 10px;
      color:white;
      background-color: #201353;
    }

</style>