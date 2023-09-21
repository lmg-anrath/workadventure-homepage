<script lang="ts" setup>
const x = ref(0);
const y = ref(0);
var mx = 0;
var my = 0;
var distance = 0;

function lerp (start: number, end: number, amt: number){
  return (1 - amt) * start + amt* end;
}

onMounted(() => {
  setInterval(() => {
    var a = (x.value + 25) - mx;
    var b = (y.value + 25) - my;
    distance = Math.sqrt(a*a + b*b);
    if (distance < 100) return;
    x.value = lerp(x.value, mx, 0.004);
    y.value = lerp(y.value, my, 0.004);
  }, 10);
  window.onmousemove = (e: MouseEvent) => {
    mx = e.pageX;
    my = e.pageY;
  }
});
</script>

<template>
  <div class="follow" :style="`top: ${y}px; left: ${x}px;`">
  </div>
</template>