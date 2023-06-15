<script setup lang="ts">
import { ref} from 'vue'

let isShow = ref(true);

function toggleShow() {
  return this.isShow = !this.isShow;
}

const VDownDrag = {
  mounted: (el: HTMLElement) => {
    let [x, y, startX, startY, moveX, moveY] = Array(6).fill(0) as number[]
    el.addEventListener('mousedown', (e: MouseEvent) => {
      // 防止鼠标移动到窗口外丢失 mouseup 事件
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
            // 防止过度拖动，超出窗口顶部外
            resY = 0
          } else if (startY + moveY >= window.innerHeight - 40) {
            // 防止过度拖动，超出窗口底部外
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
                <span style="color: #c3856b">const</span> <span style="color: #e6d321"> greeting</span> = "Hello, world!";  <br>
                <span style="color: #a7a792" >// My name is Martin AUBEUT.</span> <br>
                <span style="color: #2ec8c7" >console</span>.<span style="color: #9cbc53">log</span>(<span style="color: #e6d321">greeting</span>); <br>
                <span style="color: #a7a792" >// I'm a french web developer. </span> <br>
                <span style="color: #c3856b" >const</span> <span style="color: #e6d321"> contact</span> = {  <br>
                <span style="color: #2ec8c7" >{ email :</span>   <a href="mailto:martin.aubeut@gmail.com" target="_blank">martin.aubeut@gmail.com</a> <span style="color: #2ec8c7" >}</span>  ,  <br>
                <span style="color: #2ec8c7" >{ linkedin :</span> <span class="text-[#e6d321]"> </span>  <a href="https://www.linkedin.com/in/martin-aubeut-30452010b/" target="_blank">https://www.linkedin.com/in/martin-aubeut-30452010b/</a> <span style="color: #2ec8c7" >}</span>,  <br>
                <span style="color: #2ec8c7" >{ github :</span> <span class="text-[#e6d321]"> </span>  <a href="https://github.com/Awazez/" target="_blank">https://github.com/Awazez/</a> <span style="color: #2ec8c7" >}</span>,  <br>
                <span style="color: #2ec8c7" >{ twitter :</span> <span class="text-[#e6d321]"> </span>  <a href="https://twitter.com/AwwAzez" target="_blank">https://twitter.com/AwwAzez</a> <span style="color: #2ec8c7" >}</span>  <br>
                }
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

    