<script setup lang="ts">
    const downloadResume = () => {
        const link = document.createElement('a');
        link.href = `/files/cv.pdf`;
        link.target = '_blank';
        link.style.display = 'none';
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
    };
</script>

<template>
    <div id="hero-container" class="relative animations w-full h-full">
        <div class="relative w-full h-5/6 opacity-90 pt-28 flex flex-col justify-center items-center">
            <div class="w-full text-center lg:text-left">
                <span class="text-5xl font-bold inline">— Wel</span>
                <span class="text-5xl font-bold inline text-purple-400">come</span>
            </div>
            <div class="mt-12 indent-0 text-left flex flex-col gap-4 text-xl items-center md:items-start">
                <p>I'm Vanny, a software developer at <a href="https://mermec-engineering.com/" target="_blank" class="light-purple dark:dark-purple font-bold">Mermec Engineering</a> that loves crafting thoughtful and accessible experiences for all.</p>

                <p>This site previews a selected sample of my professional work. For full projects, feel free to contact me at <a href="mailto:hello@VannyFasanelli.com" target="_blank" class="light-purple dark:dark-purple font-bold">hello@VannyFasanelli.com</a>.</p>

                <button class="w-56 mt-5 dark:bg-white" @click="downloadResume()">Get my resume</button>
            </div>
        </div>
                
        <div class="gap-2 items-center justify-center hidden lg:flex lg:flex-col">
            <svg width="30px" height="100%" viewBox="0 0 247 390" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" style="fill-rule:evenodd;clip-rule:evenodd;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:1.5;">
                <path id="wheel" d="M123.359,79.775l0,72.843" style="fill:none;stroke-width:20px;" class="stroke-purple-400"/>
                <path id="mouse" d="M236.717,123.359c0,-62.565 -50.794,-113.359 -113.358,-113.359c-62.565,0 -113.359,50.794 -113.359,113.359l0,143.237c0,62.565 50.794,113.359 113.359,113.359c62.564,0 113.358,-50.794 113.358,-113.359l0,-143.237Z" style="fill:none;stroke-width:20px;" class="stroke-purple-400"/>
            </svg>
            <p>Scroll down</p>
        </div>
    </div>

</template>

<style scoped>

@keyframes scroll {
	0% {
		transform: translateY(0);
	}
	30% {
		transform: translateY(100px);
	}
}

svg #wheel {
	animation: scroll ease 1.5s infinite;
}

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