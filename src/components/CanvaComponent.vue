<template>
    <div class="toolbar">
        <div >
            <button title="Pinceau">
                <Paintbrush :size="30" />
            </button>

            <button title="Gomme">
                <Eraser :size="30" />
            </button>
        </div>

        <div>
            <label for="couleur">Couleur</label>
            <input type="color" name="" id="couleur" />
        </div>
        <div>
            <label for="epaisseur">Epaisseur</label>
            <input type="range" name="" id="epaisseur" min="1" max="50" />
        </div>
        <div class ="flex gap-2">
            <button>
                Nettoyer
                <RotateCcw />
            </button>
            <button>
                Télécharger
                <Download />
            </button>
        </div>
    </div>
</template>

<script setup lang="ts">
import { Paintbrush, Eraser, RotateCcw, Download } from "lucide-vue-next"

</script>