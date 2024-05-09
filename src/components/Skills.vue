<script setup lang="ts">
import { skills } from "../api/skills.json";
</script>

<template>
    <div id="skills-container" class="relative animations w-full h-full opacity-90 flex flex-col justify-center items-center">
        <div class="w-full text-center lg:text-left">
            <span class="text-5xl font-bold inline">Ski</span>
            <span class="text-5xl font-bold inline text-purple-400">lls.</span>
        </div>
        <div class="flex flex-col text-left mt-10 gap-5">
            <div class="flex flex-col">
                <p class="text-3xl text-left">Front End</p>
                <div class="indent-0 flex flex-col sm:flex-row gap-4 text-xl">
                    <button v-for="fe in skills.fe" class="mt-5 dark:bg-white cursor-default">{{fe}}</button>
                </div>
            </div>

            <div class="flex flex-col">
                <p class="text-3xl text-left">Styling & Design</p>
                <div class="indent-0 flex flex-col sm:flex-row gap-4 text-xl">
                    <button v-for="fe in skills.sd" class="mt-5 dark:bg-white cursor-default">{{fe}}</button>
                </div>
            </div>

            <div class="flex flex-col">
                <p class="text-3xl text-left">Back End</p>
                <div class="indent-0 flex flex-col sm:flex-row gap-4 text-xl">
                    <button v-for="fe in skills.be" class="mt-5 dark:bg-white cursor-default">{{fe}}</button>
                </div>
            </div>

            <div class="flex flex-col">
                <p class="text-3xl text-left">Miscellaneous</p>
                <div class="indent-0 flex flex-col sm:flex-row gap-4 text-xl">
                    <button v-for="fe in skills.misc" class="mt-5 dark:bg-white cursor-default">{{fe}}</button>
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