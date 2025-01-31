<script setup lang="ts">
import CanvaComponent from "./CanvaComponent.vue"
import ToolbarComponent from "./ToolbarComponent.vue"
</script>

<template>
    <div class="flex justify-between border-2 border-red-500 h-screen">
        <div class="flex-1 w-[25%]  border-2 border-yellow-500 ">
            <CanvaComponent></CanvaComponent>
        </div>
        <div class="flex-2 border-2 border-green-500 ">
            <ToolbarComponent></ToolbarComponent>

        </div>
    </div>
</template>
