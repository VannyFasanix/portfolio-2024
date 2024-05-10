<script setup lang="ts">
import { defineProps } from 'vue';

const props = defineProps(['proj'])

const getImage = (img: string) => {
    return new URL(`../assets/${img}`, import.meta.url).href
}
</script>

<template>
    <div id="project-detail-container" class="relative w-full flex flex-col gap-5 justify-center items-left">
        <div class="relative animations-left flex flex-col justify-center items-left">
            <span class="text-xl font-thin text-left">{{props?.proj?.title}}</span>
            <span class="text-2xl font-normal text-left"><p class="hidden md:inline">—</p> {{props?.proj?.descr}}</span>
        </div>

        <div class="relative animations-bottom flex flex-col justify-center items-left">
            <span class="text-base font-medium text-left text-purple-400">Overview</span>
            <div class="flex flex-col 2xl:flex-row gap-5 justify-center items-center 2xl:items-start">
                <div class="flex flex-col gap-5">
                    <p class="text-base font-normal text-left">{{props?.proj?.overview}}</p>
                    <a :href="props?.proj?.link" target="_blank" class="text-base font-semibold text-left !text-purple-400 hover:!text-purple-500 transition-colors">Get to the website</a>
                </div>
                <img class="max-w-full lg:max-w-xl h-1/2 lg:h-80 rounded" :src="getImage(props?.proj?.image)">

            </div>
        </div>
    </div>
</template>



<style scoped>
.animations-left {
    opacity: 0;
    -webkit-animation: slide-l 1s, fade-in 1s  forwards;
    -webkit-animation-delay: 0s;
    animation: slide-l 1s, fade-in 1s forwards;
    animation-delay: 0s;
}

@-webkit-keyframes slide-l {
    0% { left: -100px; }
    100% { left: 0; }
}

@keyframes slide-l {
    0% { left: -100px; }
    100% { left: 0; }
}

.animations-bottom {
    opacity: 0;
    -webkit-animation: slide-b 1s, fade-in 1s  forwards;
    -webkit-animation-delay: 1s;
    animation: slide-b 1s, fade-in 1s forwards;
    animation-delay: 1s;
}

@-webkit-keyframes slide-b {
    0% { bottom: -100px; }
    100% { bottom: 0; }
}

@keyframes slide-b {
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