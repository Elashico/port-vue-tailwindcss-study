<script setup="">
import about from '../assets/about.png'
import Abou from './cards/Abou.vue';

const stats = [
    {value:'+200', label:'Clients'},
    {value:'+300', label:'Projects'},
    {value:'+7', label:'Years'}
]

</script>
<template>
    <section class="text-white mt-4 md:mt-16 relative overflow-hidden"
    id="about">
        <div class="max-w-7x1 mx-auto px-6 lg:px-[14vw] md:grid md:grid-cols-2 gap-12 items-center py-16
         relative z-10">
            <div data-aos="fade-right">
                <h2 class="text-4xl md:text-5xl font-extrabold text-white whitespace-nowrap">
                    More <span class="text-primary">About</span> Me
                </h2>
                <p class="text-gray-400 text-base lg:text-lg mb-10 leading-relaxed mt-4">
                    In culpa in proident commodo. Magna nulla enim in elit minim ad. Elit fugiat id occaecat proident reprehenderit adipisicing anim aliquip excepteur commodo ullamco. 
                    <br><br>
                    Non cillum non irure veniam consequat sit eu. Nisi voluptate id et excepteur adipisicing quis ad. Proident amet eu sint cupidatat aliquip in consequat elit fugiat tempor velit enim adipisicing. Sit nisi ut occaecat ipsum ex duis reprehenderit irure consectetur ea.
                </p>
                <div class="grid grid-cols-3 gap-6 max-w-xl">
                    <Abou
                        v-for="stat in stats"
                        :key="stat.label"
                        :stat="stat"/>
                </div>
            </div>
            <!-- IMAGE -->
             <div class="mt-10 flex md:mt-4  justify-center lg:justify-end relative" data-aos="fade-left">
                <div class="relative w-64 h-64 md:w-96 md:h-120">
                    <div class="absolute inset-0 z-0 rounded-full shadow-lg border border-primary translate-x-4
                    translate-y-4"></div>
                    <div class="relative z-10 w-full h-full bg-[#111a3e] rounded-full overflow-hidden 
                    border border-[#1f1641]">
                        <img :src="about" alt="About Me" class="w-full h-full object-cover transition-transform
                        duration-500 hover:scale-110"/>
                    </div>
                </div>
             </div>
        </div>
    </section>
</template>