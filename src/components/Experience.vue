<script setup lang="ts">
import { experiences } from '../api/experiences.json'
</script>

<template>
    <div id="experience-container" class="w-full h-full animations relative">
        <div class="w-full text-right relative mb-10"> 
            <span class="text-5xl font-bold inline text-purple-400">Expe</span>
            <span class="text-5xl font-bold inline">rience.</span>
        </div>

        <div class="flex flex-col items-left justify-start w-full">
            <div v-for="exp in experiences" class="w-full flex flex-row gap-3">
                <div class="w-1/6 text-3xl flex justify-center items-center">{{exp.start}} - {{exp.end}}</div>

                <div class="w-1/12 border-l-purple-400 border-l-2" style="transition: border 0.25s">
                    
                </div>
                
                <div class="flex flex-col gap-3 text-left">
                    <a :href="exp.link" target="_blank" class="text-4xl light-purple dark:dark-purple cursor-pointer">{{exp.title}}</a>
                    <div class="text-xl">{{exp.descr}}</div>
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
    animation-delay: 1s;
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