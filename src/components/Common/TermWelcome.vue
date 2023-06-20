<script setup>
let currentDate = new Date();
console.log(currentDate);
</script>

<template>
  <div>
    
    <h2 class="title">Last login: {{currentDate}} </h2>
    <p class="paragraph">
      Type `help` for more information.
    </p>
  </div>
</template>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
.title {
    font-size: 14px;
    font-weight: bold;
    font-family: 'Poppins', sans-serif;
    margin-top: -5px;
    color:#d1059b;

}
.paragraph {
    font-size: 14px;
    font-weight: bold;
    font-family: 'Poppins', sans-serif;
    color:#d1059b;
}

</style>


