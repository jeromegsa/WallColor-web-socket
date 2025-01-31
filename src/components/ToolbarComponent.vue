<template>

    
    <div class="flex flex-col gap-4  mt-10 gap-3">

        <!-- <div>
            <h1 class="text-3xl">Outils</h1>
        </div> -->
        <div class="flex gap-5 ml-15 ">
            <button title="Pinceau" class="bg-blue-200 p-2 rounded w-20  h-20 ">
                <Paintbrush :size="40" color="blue" class="ml-3" />
            </button>

            <button title="Gomme" class="bg-red-200 p-2 rounded w-20 h-20 ">
                <Eraser :size="40" color="red" class="ml-3" />
            </button>
        </div>

        <div class="flex flex-col gap-4 ml-5 mt-15">
            <div class="flex gap-5 text-xl">
                <label for="couleur">Couleur</label>
                <input type="color" name="" id="couleur" class="w-40 " />
            </div>
            <div class="text-xl flex gap-5">
                <label for="epaisseur">Epaisseur</label>
                <input type="range" name="" id="epaisseur" min="1" max="50" class="w-40 h-10 " />
            </div>
        </div>
        <div class="flex gap-4   mt-10  ">
            <button class="bg-red-200 flex gap-2  text-red-600 text-2xl p-2 rounded ">
                <RotateCcw :size="25" color="red" class="mt-2" />
                Nettoyer
            </button>
            <button class="bg-blue-200 flex gap-2 text-blue-600 text-2xl p-2 rounded">
                <Download :size="25" color="blue" class="mt-1" />
                Télécharger
            </button>
        </div>
    </div>
</template>

<script setup lang="ts">
import { Paintbrush, Eraser, RotateCcw, Download } from "lucide-vue-next"

</script>