<script lang="ts" setup>
import '../assets/main.sass';
import '../assets/mobile.sass';

function Redirect() {
  window.open('https://play.workadventure-lmg.de', '_blank');
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
        <div class="hover"></div>
      </div>
    </div>
    <div class="background">
      <img src="https://www.lmg-anrath.de/wp-content/uploads/2017/10/LM-Logo_blau.png" alt="">
    </div>
  </div>
</template>