<script setup>
let currentDate = new Date();
console.log(currentDate);
</script>

<template>
  <div>
    
    <h2 class="title">Last login: {{currentDate}} </h2>
    <p class="paragraph">
      Bonjour amis Prévérien ! Bienvenue ! Quoi de mieux pour montrer ses compétences que de voir en vrai 
      ce que ça donne ? Oh ! La fenêtre bouge ! Mais comment ça marche ? 
      Allez voir aussi <a href="https://bookwardenapptest-d8fd.vercel.app/"> https://bookwardenapptest-d8fd.vercel.app/ <a>
      Oh ! Vraiment les catégories C qui ne bosse pas les concours. Ils sont pénibles ! 
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


