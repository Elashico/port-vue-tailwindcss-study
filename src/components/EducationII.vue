<script setup>
import educ from '../assets/educ.png'
import Educ from './cards/Educ.vue';
const educationData = [
    {
        id: "Lorem Ipsum dolor",
        degree:"Bachelors of Science in Computer Science",
        institution:"Ullamco cillum exercitation consequat",
        duration:'2020 - 2022',
        details:'Veniam est deserunt adipisicing sunt veniam ut culpa ad veniam in in sit. id irure aliqua in proident fugiat laborum cupidatat. Labore consectetur culpa deserunt eiusmod voluptate irure Lorem deserunt ir',
        academic_excellence: true
    },
    {
        id: "Lorem Ipsum dolor",
        degree:"Masters in Information Technology",
        institution:"Ullamco cillum exercitation consequat",
        duration:'2023 - 2026',
        details:'Cillum sint amet Lorem incididunt id. Officia occaecat culpa amet sint fugiat cillum. Eiusmod ut adipisicing anim tempor minimure aute. Adipisicing irure sunt ea id veniam eiusmod consectetur magna commodo fugiat.Cillum sint amet Lorem incididunt id.',
        academic_excellence: false
    }
]
</script>

<template>
    <section class="text-white py-20 overflow-hidden" id="education">
        <div class="max-w-7x1 mx-auto px-6 lg:px-[14vw]">
            <div class="mb-16">
                <p class="text-primary text-sm uppercase mb-2 tracking-widest font-semibold">
                    Learning Path</p>
                <h2 class="text-6xl md:text-5x1 font-extrabold text-white ">
                    Education</h2>
            </div>
            <div class="flex flex-col lg:flex-row  items-center gap-15">
                <!-- IMAGE EDUC -->
                <div class="hidden clg:flex w-full clg:w-5/12 justify-center lg:justify-start" data-aos="fade-right">
                    <div class="relative">
                        <div class="absolute h-full w-full z-0 p-2 translate-x-2 translate-y-2 
                        border border-primary rounded-2xl"></div>
                        <div class="relative z-10 bg-[#111a2e] rounded-2xl overflow-hidden 
                        border border-[#1f1641] ">
                            <img :src="educ" alt="Education"
                            class="w-64 h-auto md:w-96 md:h-120 object-cover transform transition-transform duration-500 hover:scale-110">
                        </div>
                    </div>
                </div>
                <!-- Educational Content -->
                <div class="grid gap-4" data-aos="fade-left">
                    <Educ
                        v-for="edu in educationData"
                        :key="edu.id"
                        :edu="edu"/>
                </div>

            </div>

        </div>

    </section>
</template>