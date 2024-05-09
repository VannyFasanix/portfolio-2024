<script setup lang="ts">
import { defineProps } from 'vue';

const props = defineProps(['proj'])

const getImage = (img: string) => {
    return new URL(`../assets/${img}`, import.meta.url).href
}

</script>

<template>
    <div class="relative w-full h-5/6 flex flex-col gap-5 justify-center items-left">
        <div class="flex flex-col justify-center items-left">
            <span class="text-xl font-thin text-left">{{props?.proj?.title}}</span>
            <span class="text-2xl font-normal text-left">— {{props?.proj?.descr}}</span>
        </div>

        <div class="flex flex-col justify-center items-left">
            <span class="text-base font-medium text-left text-purple-400">Overview</span>
            <div class="flex flex-col 2xl:flex-row gap-5 justify-center items-center 2xl:items-start">
                <p class="text-base font-normal text-left">{{props?.proj?.overview}}</p>
                <img class="max-w-full lg:max-w-xl h-1/2 lg:h-80 rounded" :src="getImage(props?.proj?.image)">

            </div>
        </div>
    </div>
</template>



<style scoped>
    
</style>