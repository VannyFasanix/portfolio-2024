<script setup lang="ts">
import { projects } from '../api/projects.json'

const emits = defineEmits(["openDetail"]);

const getImage = (img: string) => {
    return new URL(`../assets/${img}`, import.meta.url).href
}

const openDetail = (proj: any) => {
    emits('openDetail', proj)
}
</script>

<template>
    <div id="projects-container" class="w-full h-full animations relative">
        <div class="w-full text-center lg:text-right relative mb-10"> 
            <span class="text-5xl font-bold inline text-purple-400">Pro</span>
            <span class="text-5xl font-bold inline">jects <p class="hidden md:inline">—</p></span>
        </div>
        <div v-for="proj in projects" class="w-full flex flex-col">
            <div class="mt-3 w-full flex flex-col sm:flex-row gap-5 items-center">
                <a class="w-full lg:w-1/2 cursor-pointer"><img class="max-w-full min-w-full h-44 lg:h-80 rounded" :src="getImage(proj.image)" @click="openDetail(proj)"></a>
                <div class="w-full lg:w-1/2 flex flex-col text-left">
                    <a class="light-purple dark:dark-purple font-bold cursor-pointer" @click="openDetail(proj)">{{ proj.title }}</a>
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
    animation-delay: 2s;
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