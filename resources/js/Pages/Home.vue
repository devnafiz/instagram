<script setup>
import { ref, onMounted, toRefs } from 'vue'
import { Head, Link, router } from '@inertiajs/vue3';
import MainLayout from '@/Layouts/MainLayout.vue';

import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Navigation } from 'vue3-carousel'
import DotsHorizontal from 'vue-material-design-icons/DotsHorizontal.vue';

let wWidth=ref(window.innerHeight)
let currentSlide = ref(0)
let currentPost = ref(null)
let openOverLay = ref(false)

onMounted(()=>{

 window.addEventListener('resize',()=>{

    wWidth.value =window.innerWidth
 })

})


</script>

<template>
    <Head title="instagram" />
    <MainLayout>
        <div class=" mx-auto lg:pl-[80px] pl-0 ">
            <Carousel></Carousel>
        </div>
         
    
    </MainLayout>
   


   


  
</template>

<style>

</style>
