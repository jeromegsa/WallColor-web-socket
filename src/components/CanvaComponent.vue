<template  >

    <canvas class="  border border-red-500" ref="canvasRef" >

    </canvas>
</template>
<script  setup lang="ts">
import {ref} from 'vue'
import {onMounted} from 'vue'
const canvasRef=ref<HTMLCanvasElement |null >(null);
onMounted(()=>{
    const canvas=canvasRef.value;
    if(!canvas) return;
    const ctx=canvas?.getContext('2d');
    
//     ctx.fillStyle = "green";
// ctx.fillRect(10, 10, 100, 100); // Un carré vert
// ctx.strokeStyle = "red";
// ctx.strokeRect(150, 10, 100, 100); // Un carré contour rouge

ctx.beginPath();
ctx.moveTo(50, 50);
ctx.lineTo(200, 50);
ctx.lineTo(200, 200);
ctx.stroke();
})


</script>
