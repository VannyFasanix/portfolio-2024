<script setup lang="ts">
</script>

<template>
    <div class="relative animations w-full h-full opacity-90 pt-28 flex flex-col justify-center items-center">
        <div class="w-full text-left">
            <span class="text-5xl font-bold inline">-- Wel</span>
            <span class="text-5xl font-bold inline text-purple-400">come.</span>
        </div>
        <div class="ml-24 mr-24 mt-12 indent-0 text-left flex flex-col gap-4 text-xl">
            <p>I'm Vanny, a software developer at <a href="https://mermec-engineering.com/" target="_blank" class="text-purple-200 font-bold text-hover">Mermec Engineering</a> that loves crafting thoughtful and accessible experiences for all.</p>

            <p>This site previews a selected sample of my professional work. For full projects, feel free to contact me at hello@VannyFasanelli.com.</p>
        </div>
    </div>
</template>

<style scoped>
.animations {
    opacity: 0;
    -webkit-animation: slide 1s, fade-in 1s  forwards;
    -webkit-animation-delay: 0s;
    animation: slide 1s, fade-in 1s forwards;
    animation-delay: 0s;
}

@-webkit-keyframes slide {
    0% { left: -100px; }
    100% { left: 0; }
}

@keyframes slide {
    0% { left: -100px; }
    100% { left: 0; }
}

@-webkit-keyframes fade-in {
    100% { opacity: 0; }
}

@keyframes fade-in {
    100% { opacity: 1; }
}

</style>