

<template>

  <n-space vertical size="small" class="container-md mx-auto">
    <n-layout >
      <div class="flex  flex-wrap justify-center text-center">
        <n-button class="m-2 block w-1/4" size="medium" type="primary" ghost="true" v-for="(value,index) in audioSrc" @click="player(index)">{{value.text}}</n-button>
      
      </div>

    </n-layout>

  </n-space>

</template>


<script setup lang="ts">
import { ref } from 'vue'
const audio = new Audio();
interface audiosrc{
  text:string,
  src:string
}
const audioSrc:Array<audiosrc> = [{text:"卧",src:"/src-tauri/music/11wo.mp3"},{text:"槽",src:"/src-tauri/music/12cao.mp3"},{text:"说",src:"/src-tauri/music/13shuo.mp3"},
{text:"藏话",src:"/src-tauri/music/14canghua.mp3"},{text:"我",src:"src-tauri/music/21wo.mp3"},{text:"测",src:"src-tauri/music/22ce.mp3"},{text:"你们",src:"src-tauri/music/23nimen.mp3"},
{text:"码",src:"src-tauri/music/24ma.mp3"},{text:"芝士雪豹",src:"src-tauri/music/zhishixuebao.mp3"},{text:"芝士猞猁",src:"src-tauri/music/zhishisheli.mp3"},{text:"芝士狐狸",src:"src-tauri/music/zhishihuli.mp3"},{text:"zood",src:"src-tauri/music/zood.mp3"}]

const player=(index:number)=>{
  audio.pause();
  audio.src = audioSrc[index].src;
  audio.play();
}

</script>
<style scoped>
</style>
