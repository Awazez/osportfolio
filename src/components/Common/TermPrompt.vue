<template>
 <section class="terminalBody">          
            <div class="terminalPrompt">            
              <span class="terminalPromptUser">awazez@mac-mini-de-Martin ~ %</span>                               
              <span class="terminalPromptCursor"></span> 
              <input>
              
            </div>        
          </section>

</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

.terminalPrompt {  
  display: flex;
}
.terminalPromptUser {  
  font-size: 14px;
  font-weight: bold;
  font-family: 'Poppins', sans-serif;
  color:#d1059b;
}

.terminalPromptCursor {  
  display: block;  
  height: 17px;  
  width: 8px;  
  margin-left: 9px;  
  animation: blink 1200ms linear infinite;

}

</style>