<script setup lang="ts">
import Navbar from './Navbar.vue'
import Hero from './Hero.vue'
import Projects from './Projects.vue'
import About from './About.vue';
import Skills from './Skills.vue';
import Experience from './Experience.vue';
</script>

<template>
    <div class="h-screen" style="width: 1080px">
        <div class="h-10 p-1">
            <Navbar/>
        </div>
        <div class="h-full p-1">
            <Hero/>
        </div>
        <div class="p-1">
            <Experience/>
        </div>
        <div class="mt-32 p-1">
            <Skills/>
        </div>
        <div class="mt-32 p-1">
            <Projects/>
        </div>
        <div class="mt-12 p-1">
            <About/>
        </div>
        <div class="h-32 flex justify-center items-center relative">
            All rights reserved 
        </div>
    </div>
</template>

<style scoped>
</style>