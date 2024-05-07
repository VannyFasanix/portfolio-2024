<script setup lang="ts">
import { projects } from '../api/projects.json'
const getImage = (img: string) => {
    return new URL(`../assets/${img}`, import.meta.url).href
}
</script>

<template>
    <div id="projects-container" class="w-full h-full animations relative">
        <div class="w-full text-right relative mb-10"> 
            <span class="text-5xl font-bold inline text-purple-400">Pro</span>
            <span class="text-5xl font-bold inline">jects.</span>
        </div>
        <div v-for="proj in projects" class="flex flex-col">
            <div class="mt-3 flex flex-row gap-5 items-center">
                <a :href="proj.link" target="_blank"><img class="max-w-xl h-80 rounded" :src="getImage(proj.image)"></a>
                <div class="flex flex-col text-left">
                    <a :href="proj.link" target="_blank" class="light-purple dark:dark-purple font-bold">{{ proj.title }}</a>
                    <p>{{proj.descr}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.animations {
    opacity: 0;
    -webkit-animation: slide 1s, fade-in 1s  forwards;
    -webkit-animation-delay: 1s;
    animation: slide 1s, fade-in 1s forwards;
    animation-delay: 2;
}

@-webkit-keyframes slide {
    0% { bottom: -100px; }
    100% { bottom: 0; }
}

@keyframes slide {
    0% { bottom: -100px; }
    100% { bottom: 0; }
}

@-webkit-keyframes fade-in {
    100% { opacity: 0; }
}

@keyframes fade-in {
    100% { opacity: 1; }
}

</style>