<script setup lang="ts">
import { ref } from 'vue';

    const emits = defineEmits(["goHome"]);

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

        emits('goHome', selector)
        
        setTimeout(() => {
            if(element)
                element.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }, 200)

    }

    const closeNavDropdown = () => {
        
        const menuToggle: any = document.getElementById('menu-toggle');

        if (menuToggle && menuToggle?.checked) {
            menuToggle.checked = false;
        }
    }
</script>

<template>
    <div id="navbar-container" class="fixed block left-0 md:flex md:flex-row animations w-full max-w-full z-40 justify-center">
        <a href="#hero" class="nav-link nav-link-ltr z-40 !hidden 2xl:!inline-block text-left cursor-pointer" @click="scrollTo('hero-container')">Vanny Fasanelli</a>
        <div class="w-1/6 !hidden 2xl:!inline-block"></div>

        <div class="w-full md:hidden bt-custom-nav dark:bt-custom-nav-dark custom-nav">
            <input type="checkbox" id="menu-toggle" class="hidden">
            <label for="menu-toggle" class="hamburger-icon">
                <span class="bg-span-hamburger"></span>
                <span class="bg-span-hamburger"></span>
                <span class="bg-span-hamburger"></span>
            </label>
 
            <nav class="top-0 w-full relative z-40">
                <ul class="flex flex-col items-center z-40">
                    <li><a href="#projects" class="nav-link nav-link-ltr text-white px-4 py-2" @click="scrollTo('experience-container'), closeNavDropdown()">Experiences</a></li>
                    <li><a href="#projects" class="nav-link nav-link-ltr text-white px-4 py-2" @click="scrollTo('skills-container'), closeNavDropdown()">Skills</a></li>
                    <li><a href="#projects" class="nav-link nav-link-ltr text-white px-4 py-2" @click="scrollTo('projects-container'), closeNavDropdown()">Projects</a></li>
                    <li><a href="#about" class="nav-link nav-link-ltr text-white px-4 py-2" @click="scrollTo('about-container'), closeNavDropdown()">About me</a></li>
                    <li><a class="nav-link nav-link-ltr text-white px-4 py-2 cursor-pointer" @click="changeTheme()">{{theme}} theme</a></li>
                </ul>
            </nav>
        </div>

        <nav class="top-0 w-auto relative z-40">
            <ul class="hidden md:flex flex-row items-center z-40">
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

.custom-nav {
    border-bottom: rgba(0, 0, 0, 0.2) 1px solid;
    background-color: rgba(242, 242, 242, 0.8);

    .dark & {
        border-bottom: rgba(255, 255, 255, 0.2) 1px solid;
        background-color: rgba(0, 0, 0, 0.8);
        
    }
}

.bg-span-hamburger {
    background-color: rgba(0, 0, 0, 0.5) !important;

    .dark & {
        background-color: rgba(242, 242, 242, 0.5) !important;
    }
}

.hamburger-icon {
display: inline-block;
cursor: pointer;
padding-top: 10px;
}
.hamburger-icon span {
display: block;
height: 2px;
width: 25px;
margin: 5px auto;
transition: all 0.3s ease-in-out;
}

#menu-toggle:checked + .hamburger-icon span:nth-child(1) {
transform: rotate(45deg) translate(5px, 5px);
}
#menu-toggle:checked + .hamburger-icon span:nth-child(2) {
opacity: 0;
}
#menu-toggle:checked + .hamburger-icon span:nth-child(3) {
transform: rotate(-45deg) translate(5px, -5px);
}

#menu-toggle:not(:checked) ~ nav {
display: none;
}

.bg-custom-nav {
   background-color: #eee;
}

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
