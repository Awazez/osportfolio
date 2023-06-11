<script setup>

</script>

<template>
      <div class="container">
        <img @click="$emit('someEvent')" src="../assets/terminal.png">
    <span>Terminal</span>
    </div>
</template>

<style scoped>

span {
    color:white;
    margin-left: -62px;
}

img {
  width: 60px;
  height: 60px;
  margin-bottom: 8px;
}
.container {
    margin-left: 900px;
    margin-top: 15px;
}

</style>