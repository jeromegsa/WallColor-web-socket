<template>
    <div class="flex flex-col gap-4  ml-8 mt-10 gap-3">
        <div class="flex gap-5 ml-15">
            <button title="Pinceau" class="bg-blue-200 p-2 rounded">
                <Paintbrush :size="30" color="blue" />
            </button>

            <button title="Gomme" class="bg-red-200 p-2 rounded ">
                <Eraser :size="30" color="red" />
            </button>
        </div>

        <div class="flex flex-col gap-4 ml-5 mt-15">
            <div class="flex gap-5">
                <label for="couleur">Couleur</label>
                <input type="color" name="" id="couleur" class="w-40 " />
            </div>
            <div>
                <label for="epaisseur">Epaisseur</label>
                <input type="range" name="" id="epaisseur" min="1" max="50" />
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