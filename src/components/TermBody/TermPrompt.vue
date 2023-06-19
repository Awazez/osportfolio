<template>
 <section id="terminal__body">          
            <div id="terminal__prompt">            
              <span id="terminal__prompt--user">awazez@mac-de-awazez:</span>            
              <span id="terminal__prompt--location">~</span>            
              <span id="terminal__prompt--bling">$</span>            
              <span id="terminal__prompt--cursor"></span>   
              
            </div>        
          </section>

</template>

<style scoped>

input {  
  width: 100px;
  height: 20px;
  color: black;
  border: none;
}

#terminal__prompt {  
  display: flex;
}
#terminal__prompt--user {  
  color: #7eda28;
}
#terminal__prompt--location { 
  color: #4878c0;
}
#terminal__prompt--bling {  
  color: #dddddd;
}
#terminal__prompt--cursor {  
  display: block;  
  height: 17px;  
  width: 8px;  
  margin-left: 9px;  
  animation: blink 1200ms linear infinite;

}

</style>