<script setup lang="ts">
import { ref } from 'vue';


    let theme = ref(document.documentElement.classList.contains('dark') ? 'light' : 'dark')

    const changeTheme = () => {

        if (!document.documentElement.classList.contains('dark')) {
            document.documentElement.classList.add('dark')
            theme.value = 'light'
        } else {
            document.documentElement.classList.remove('dark')
            theme.value = 'dark'
        }
    }

    const scrollTo = (selector: string) => {
        const element: any = document.getElementById(selector);
        
        if(element)
            element.scrollIntoView({ behavior: 'smooth', block: 'center' });
    }
</script>

<template>
    <div class="fixed animations flex flex-row gap-72 z-40">
        <a class="vanny-fasanelli w-80 z-40">Vanny Fasanelli</a>
        <nav class="top-0 w-full relative z-40">
            <ul class="flex justify-end z-40">
                <li><a href="#projects" class="nav-link nav-link-ltr text-white px-4 py-2" @click="scrollTo('experience-container')">Experiences</a></li>
                <li><a href="#projects" class="nav-link nav-link-ltr text-white px-4 py-2" @click="scrollTo('skills-container')">Skills</a></li>
                <li><a href="#projects" class="nav-link nav-link-ltr text-white px-4 py-2" @click="scrollTo('projects-container')">Projects</a></li>
                <li><a href="#about" class="nav-link nav-link-ltr text-white px-4 py-2" @click="scrollTo('about-container')">About me</a></li>
                <li><a class="nav-link nav-link-ltr text-white px-4 py-2 cursor-pointer" @click="changeTheme()">{{theme}} theme</a></li>
            </ul>
        </nav>
    </div>
</template>

<style scoped>
.animations {
    opacity: 0;
    -webkit-animation: fade-in 1s  forwards;
    -webkit-animation-delay: 1s;
    animation: fade-in 1s forwards;
    animation-delay: 1s;
}

@-webkit-keyframes fade-in {
    100% { opacity: 0; }
}

@keyframes fade-in {
    100% { opacity: 1; }
}
</style>