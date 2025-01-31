<template>

    <canvas class="  border border-red-500 " ref="canvasRef" @mousedown="startDrawing" @mousemove="draw">

    </canvas>
</template>
<script setup lang="ts">
import { ref, onMounted } from "vue";
// récupérer
const canvasRef = ref<HTMLCanvasElement | null>(null);
// coordonnées du dernier point
const lastPoint = ref<{ x: number; y: number } | null>();
// fonction qui sera appelée au commencement du dessin
const startDrawing = (event: MouseEvent) => {
  console.log("toolbar", toolbar);
  // récupérer l'événement premier clic de la souris
  lastPoint.value = {
    x: event.clientX,
    y: event.clientY,
  };
};
const resizeCanvas = () => {
  // Récupération de l'élément toolbar du conteneur Home
const toolbar = document.querySelector(".toolbar")
  const canvas = canvasRef.value;
  if (!canvas || !toolbar) return;
  console.log("toolbar", toolbar);

  canvas.width = window.innerWidth - toolbar.clientWidth;
  canvas.height = window.innerHeight ;
};

// Dessiner
const draw = (e: MouseEvent) => {
  // récupération de l'élément canvas depuis le html
  const canvas = canvasRef.value;
  // si l'élément n'existe pas , ne rien retourner
  if (!canvas) return;

  const rect = canvas.getBoundingClientRect();
  // si le dernier point n'existe  pas , ne rien retourner
  if (!lastPoint.value) return;

  // coordonnées du point actuel
  const currentPoint = {
    x: e.clientX - rect.left,
    y: e.clientY - rect.top,
  };

  // spécifier le context à l'élément canvas
  const ctx = canvas.getContext("2d");
  // si l'élément n'existe pas, ne rien retourner
  if (!ctx) return;

  ctx.beginPath();
  // utiliser la couleur des traits
  ctx.strokeStyle = "green";
  // tracer le(s) trait(s) depuis le dernier point
  ctx.moveTo(lastPoint.value.x, lastPoint.value.y);
  //  jusqu'au point actuel
  ctx.lineTo(currentPoint.x, currentPoint.y);
  ctx.stroke();

  lastPoint.value = currentPoint;
};

onMounted(() => {
  // appel de la fonction de redimension lors du montage du composant
  resizeCanvas();
});
</script>
