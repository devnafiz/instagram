<script setup>
import { ref, onMounted, toRefs } from 'vue'
import { Head, Link, router } from '@inertiajs/vue3';
import  MainLayout  from '@/Layouts/MainLayout.vue';

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
    <Head title="instagram"/>
    <MainLayout>
        <div class=" mx-auto lg:pl-0 md:pl-[80px] pl-0 ">
            <Carousel
            
              v-model="currentSlide"
              class="max-w-[700px] mx-auto"
              :items-to-show="wWidth >=768 ? 8 : 6"
              :items-to-scroll="4"
              :wrap-around="true"
              :transition="500"
              snapAlign ="start"
            >
             <Slide v-for="slide in 10" :key="slide" class="h-40">
              <Link href="/" class=" relative mx-auto text-center mt-4 px-2 cursor-pointer">
                 <div  class=" absolute z-[-1] -top-[5px] left-[4px] rounded-full rotate-4 w-[64px] h-[64px] contrast-[1.3] bg-gradient-to-t from-yellow-300 to-purple-500 via-red-500">
                    

                    <div class="rounded-full ml-[3px] mt-[3px] w-[58px] h-[58px] bg-white">
                     <img class=" rounded-full w-[56px] h-[56px] -mt-[1px]" src="https://yt3.ggpht.com/yti/AHXOFjXsIzb-vQyYb6kHey0ZrxH--n6xCUmo9hIu-qvm=s88-c-k-c0x00ffffff-no-rj-mo">
                     <div class="text-xs mt-2 w-[60px] truncate text-ellipsis overflow-hidden">Name Here</div>
                    </div>
                    

                 </div>
              </Link>
            </Slide>
               
            <template #addons>
                    <Navigation />
                </template>
            </Carousel>


            <div id="Posts" class=" px-4 max-w-[600px] mx-auto mt-10">
                <div class=" flex items-center justify-between py-2">
                    <div class=" flex items-center">
                        <Link href="/" class="flex items-center">
                            <img  class=" rounded-full w-[38px] h-[38px]" src="https://yt3.ggpht.com/yti/AHXOFjXsIzb-vQyYb6kHey0ZrxH--n6xCUmo9hIu-qvm=s88-c-k-c0x00ffffff-no-rj-mo"/>
                            <div class="ml-4 font-extrabold text-[15px]">Name Here</div>
                        
                        </Link>
                        <div class="flex items-center text-[15px] text-gray-500">
                            <span class=" -mt-5 ml-2 mr-[5px] text-[35px]">.</span>
                            <div> 1200.9.09</div>

                        </div>

                    </div>
                    <DotsHorizontal class=" cursor-pointer" :size="27"/>

                </div>
                <div class="bg-black rounded-lg w-full min-h-[400px] flex items-center">
                    <img class="mx-auto w-full" src="https://yt3.ggpht.com/e9o-24_frmNSSVvjS47rT8qCHgsHNiedqgXbzmrmpsj6H1ketcufR1B9vLXTZRa30krRksPj=s88-c-k-c0x00ffffff-no-rj" />
                </div>

            </div>
        </div>
         
    
    </MainLayout>
   


   


  
</template>

<style>
.carousel__prev,
    .carousel__next,
    .carousel__prev:hover,
    .carousel__next:hover {
        color: rgb(49, 49, 49);
        background-color: rgb(255, 255, 255);
        border-radius: 100%;
        margin: 0 20px;
    }
</style>
