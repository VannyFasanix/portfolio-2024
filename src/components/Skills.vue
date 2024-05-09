<script setup lang="ts">
import { skills } from "../api/skills.json";
</script>

<template>
    <div id="skills-container" class="relative animations w-full h-full opacity-90 flex flex-col justify-center items-center">
        <div class="w-full text-center lg:text-left">
            <span class="text-5xl font-bold inline"><p class="hidden md:inline">—</p> Ski</span>
            <span class="text-5xl font-bold inline text-purple-400">lls</span>
        </div>
        <div class="flex flex-col text-left mt-10 gap-5">
            <div v-for="(skill, index) in skills" class="flex flex-col">
                <p class="text-3xl text-center md:text-left">{{skill.name}}</p>
                <div class="indent-0 flex flex-col sm:flex-wrap lg:flex-row gap-4 text-xl">
                    <button v-for="s in skills[index].list" class="mt-5 dark:bg-white cursor-default">{{s}}</button>
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
    animation-delay: 1.5s;
}

@-webkit-keyframes slide {
    0% { top: -100px; }
    100% { top: 0; }
}

@keyframes slide {
    0% { top: -100px; }
    100% { top: 0; }
}

@-webkit-keyframes fade-in {
    100% { opacity: 0; }
}

@keyframes fade-in {
    100% { opacity: 1; }
}
</style>