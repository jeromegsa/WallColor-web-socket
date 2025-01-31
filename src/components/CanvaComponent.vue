<template>

    <canvas class="  border border-red-500 h-full" ref="canvasRef" @mousedown="startDrawing" @mousemove="draw">

    </canvas>
</template>
<script setup lang="ts">
import { ref } from 'vue'
import { onMounted } from 'vue'
const canvasRef = ref<HTMLCanvasElement | null>(null);
const lastPoint = ref<{ x: number, y: number } | null>(null);

const startDrawing = (e: MouseEvent) => {
    console.log('start drawing', e);
    lastPoint.value = {
        x: e.clientX,
        y: e.clientY
    }
    console.log('lastPoint', lastPoint.value);
}
const draw = ((e: MouseEvent) => {
  const currentPoint={
    x:e.clientX,
    y:e.clientY
  }    
  const canvas = canvasRef.value;
    if (!canvas) return;
    const ctx = canvas?.getContext('2d');
  console.log('currentPoint',currentPoint);
    if(!lastPoint.value) return;


    ctx.beginPath();
    ctx.strokeStyle = "red";
    ctx.moveTo(lastPoint.value.x, lastPoint.value.y);
    ctx.lineTo(currentPoint.x, currentPoint.y);
    ctx.stroke();
})
onMounted(() => {
    

    //     ctx.fillStyle = "green";
    // ctx.fillRect(10, 10, 100, 100); // Un carré vert
    // ctx.strokeStyle = "red";
    // ctx.strokeRect(150, 10, 100, 100); // Un carré contour rouge

})


</script>
