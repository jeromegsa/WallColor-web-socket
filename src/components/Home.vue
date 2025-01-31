<script setup lang="ts">
import CanvaComponent from "./CanvaComponent.vue"
import ToolbarComponent from "./ToolbarComponent.vue"
</script>

<template>
    
    <div class="flex  h-screen">
        
        <div class=" w-[30%]   bg-gray-100  gap-2 p-4">
            <ToolbarComponent></ToolbarComponent>
        </div>

        <div class="flex-1 border-2 ">
            <CanvaComponent></CanvaComponent>
        </div>
    </div>
</template>
