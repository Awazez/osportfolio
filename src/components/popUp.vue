<script setup lang="ts">
import { ref} from 'vue'
import TermWelcome from "./TermBody/TermWelcome.vue"
import TermPrompt from "./TermBody/TermPrompt.vue"

let isShow = ref(true);

function toggleShow() {
  return this.isShow = !this.isShow;
}

const VDownDrag = {
  mounted: (el: HTMLElement) => {
    let [x, y, startX, startY, moveX, moveY] = Array(6).fill(0) as number[]
    el.addEventListener('mousedown', (e: MouseEvent) => {
      e.stopPropagation()
      e.preventDefault()
      x = e.pageX
      y = e.pageY
      startX = el.offsetLeft
      startY = el.offsetTop
      window.addEventListener('mousemove', fn)
      window.addEventListener('mouseup', () => {
        window.removeEventListener('mousemove', fn)
      })
      function fn(e: MouseEvent) {
        e.stopImmediatePropagation()
        requestAnimationFrame(() => {
          moveX = e.pageX - x
          moveY = e.pageY - y
          el.style.left = `${startX + moveX}px`
          let resY = 0
          if (startY + moveY <= 0) {
            resY = 0
          } else if (startY + moveY >= window.innerHeight - 40) {
            resY = window.innerHeight - 40
          } else {
            resY = startY + moveY
          }
          el.style.top = `${resY}px`
        })
      }
    })
  }
}



</script>
<template>
    <div>
        <div class="box" v-down-drag>
        <div class="grid place-items-center h-screen">
        <div v-show="isShow" class="">
          <div ref="index"  class="upper-box" >
            <div class="button-box">
                <span @click=toggleShow() style="background-color: #ff5f57" class="button" > </span>
                <span style="background-color: #febc2e" class="button"> </span>
                <span style="background-color: #27c840"  class="button"> </span>
            </div>
          </div>
            <div class="inner-box">
              
              <div class="text-box">
             
                <TermWelcome/>
                <TermPrompt/>
               
              </div>
            </div>
        </div>
    </div>
    </div>
  </div>
    </template>
    

    <style scoped>

    #index {
      position: fixed;
    }

    a {
      color: white;
    }
    

    .button  {
      background-color: black;
      display: inline-block;
      width: 12px;
      height: 12px;
      border-radius: 50%;
      margin-top: 11px;
      margin-left: 8px;
    }
    
    img {
      width: 61.38px;
      height: 40.92px;
    }


    .box {
      position: absolute;
      top: 50px;
      left: 200px;

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
      color:white;
      background-color: #201353;
    }

    .text-box {
      padding: 10px;
    }

    </style>

    