<script setup>
import { Layout, Cpu, Terminal, Layers } from 'lucide-vue-next';
import Skil from './cards/Skil.vue';
import Work from './cards/Work.vue';

const skills = [
    {
        id: 1,
        name: 'React Js',
        width: '85%',
        icons: Layout
    },
    {
        id: 2,
        name: 'Vue Js',
        width: '98%',
        icons: Cpu
    },
    {
        id: 3,
        name: 'JavaScript',
        width: '98%',
        icons: Terminal
    },
    {
        id: 4,
        name: 'Figma',
        width: '91%',
        icons: Layers
    }
]
const expriences = [
    {
        id: 1,
        role: 'Software Engineer',
        company: 'Microsoft',
        date: 'Mar 2023 - Sep 2024'
    },
    {
        id: 2,
        role: 'Frontend Developer',
        company: 'Spotify',
        date: 'Jan 2022 - Mar 2023'
    }
]

</script>

<template >
    <section class="text-white py-20 relative overflow-hidden" id="skills">
        <div class="max-w-7xl mx-auto px-6 lg:px-16 relative z-10">
            <div class="grid md:grid-cols-2 gap-16 items-start">
                <!-- Skills left -->
                <div data-aos="fade-right">
                    <h2 class="text-4xl md:text-5xl font-extrabold mb-12">
                        Technical <span class="text-primary">Skills</span>
                    </h2>
                    <div class="space-y-8">
                        <Skil 
                        v-for="skil in skills"
                        :key="skil.id"
                        :skil="skil"/>
                    </div>
                </div>
                <!-- skills right -->
                <div data-aos="fade-left" >
                    <h2 class="text-4xl md:text-5xl font-extrabold mb-12">
                        Work <span class="text-primary">Experience</span>
                    </h2>
                    <div class="space-y-8">
                        <Work 
                        v-for="exp in expriences"
                        :key="exp.id"
                        :exp="exp"/>
                    </div>
                </div>

            </div>
        </div>  
    </section>
</template>