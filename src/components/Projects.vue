<script setup lang="ts">
import { projects } from '../api/projects.json'
const getImage = (img: string) => {
    return new URL(`../assets/${img}`, import.meta.url).href
}
</script>

<template>
    <div class="w-full h-full">
        <div class="w-full text-right relative right-52 mb-10"> 
            <span class="text-5xl font-bold inline text-purple-400">-- Pro</span>
            <span class="text-5xl font-bold inline">jects.</span>
        </div>
        <div v-for="proj in projects" class="flex flex-col">
            <div class="mt-3 flex flex-row gap-5 items-center">
                <a :href="proj.link" target="_blank"><img class="max-w-xl h-80 rounded" :src="getImage(proj.image)"></a>
                <div class="flex flex-col text-left">
                    <a :href="proj.link" target="_blank" class="text-purple-200 font-bold text-hover">{{ proj.title }}</a>
                    <p>{{proj.descr}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
</style>