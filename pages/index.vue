<script lang="ts" setup>
import '../assets/main.sass';
import '../assets/mobile.sass';

const hover = ref<HTMLDivElement | null>(null);

function Redirect() {
  console.log(hover.value)
  if (!hover.value) return;
  hover.value.style.transition = 'padding 1.5s ease-in-out, transform 1.5s ease-in-out, border-radius 1.5s';
  const fill = window.innerWidth - hover.value.clientWidth;
  hover.value.style.padding = `${fill}px`;
  hover.value.style.transform = `translateX(-${fill}px) translateY(-${fill}px)`;
  setTimeout(() => {
    window.open('https://play.workadventure-lmg.de', '_blank');
    setTimeout(() => {
      if (!hover.value) return;
      hover.value.style.transition = 'padding 0.5s, transform 0.5s, border-radius 0.5s';
      hover.value.style.padding = ``;
      hover.value.style.transform = ``;
    }, 100);
  }, 1000);
}
</script>

<template>
  <div>
    <div class="main-container">
      <div class="heading">
        WORKADVENTURE<div>LMG</div>
      </div>
      <div class="play-button">
        <button @click="Redirect()">JETZT ÖFFNEN!</button>
        <div class="hover" ref="hover"></div>
      </div>
    </div>
    <div class="background">
      <FollowCursor />
      <img src="https://www.lmg-anrath.de/wp-content/uploads/2017/10/LM-Logo_blau.png" alt="">
    </div>
  </div>
</template>