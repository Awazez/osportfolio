<script setup lang="ts">
var currentDate = new Date();
console.log(currentDate);

</script>

<template>
  <div>
    
    <h2 class="title">{{currentDate}} </h2>
    <p class="paragraph">
      Type `help` for more information.
    </p>
  </div>
</template>
<style scoped>
.title {
    font-size: 14px;
    font-weight: bold;
    font-family: 'Courier New', Courier, monospace;
    color:white;

}
.paragraph {
    font-size: 14px;
    font-weight: bold;
    font-family: 'Courier New', Courier, monospace;
    color:white;
}

</style>


