<script setup lang="ts">
import Navbar from './Navbar.vue'
import Hero from './Hero.vue'
import Projects from './Projects.vue'
import About from './About.vue';
import Skills from './Skills.vue';
import Experience from './Experience.vue';
import ProjectDetail from './ProjectDetail.vue';
import {ref} from 'vue'

const selProject = ref<any>(null);

const showDetail = ref<boolean>(false);

const onOpenDetail = (proj: any) => {
    showDetail.value = true
    const element: any = document.getElementById('hero-container');
    
    if(element)
        element.scrollIntoView({ behavior: 'smooth', block: 'start' });

    setTimeout(() => (selProject.value = proj, showDetail.value = true), 200)
}

const onGoHome = () => {
    selProject.value = null;
    showDetail.value = false

    const selector = `[id*="-container"], [class*="-container"]`;
    
    const elements = document.querySelectorAll(selector);

    elements.forEach(element => {
        element.classList.remove("animations");
    });

}
</script>

<template>
    <div class="h-screen flex flex-col items-center custom-width">
        <div class="w-full">
            <Navbar :onGoHome="onGoHome"/>
        </div>

        <div v-show="selProject == null && showDetail == false" class="w-full h-full">
            <div class="h-screen w-full p-1">
                <Hero/>
            </div>
            <div class="p-1 w-full">
                <Experience/>
            </div>
            <div class="mt-32 p-1 w-full">
                <Skills/>
            </div>
            <div class="mt-32 p-1 w-full">
                <Projects :onOpenDetail="onOpenDetail"/>
            </div>
            <div class="mt-12 p-1 w-full">
                <About/>
            </div>
            <div class="h-32 flex justify-center items-center relative">
                <p class="font-extralight text-xs">All rights reserved 2024 @ Vanny Fasanelli</p>
            </div>
        </div>

        <div v-if="selProject != null && showDetail == true" class="w-full h-full p-1 justify-center flex flex-col mt-20">
            <ProjectDetail :proj="selProject"/>

            <div class="h-32 flex justify-center items-center relative">
                <p class="font-extralight text-xs">All rights reserved 2024 @ Vanny Fasanelli</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
@media (min-width: 1024px) {
    /* Schermi grandi */
    .custom-width {
      width: 55vw;
    }
  }
  
  @media (max-width: 1023px) {
    /* Schermi medi e piccoli */
    .custom-width {
      width: 85vw;
    }
  }
</style>
