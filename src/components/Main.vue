<script setup lang="ts">
import Navbar from './Navbar.vue'
import Hero from './Hero.vue'
import Projects from './Projects.vue'
</script>

<template>
    <div class="w-full h-screen">
        <div class="h-10 p-1" style="width: 1080px">
            <Navbar/>
        </div>
        <div class="h-96 mt-32 p-1" style="width: 1080px">
            <Hero/>
        </div>
        <div class="mt-32 p-1" style="width: 1080px">
            <Projects/>
        </div>
        <div class="h-32"></div>
    </div>
</template>

<style scoped>
</style>