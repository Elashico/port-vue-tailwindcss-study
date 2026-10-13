<script setup>
import { Award, ExternalLink, ShieldCheck } from 'lucide-vue-next';


defineProps({
    cert: {
        type: Object,
        required: true
    }
})

</script>

<template>
    <div data-aos="zoom-in" class="relative group bg-[#111a3e] border border-[#1f1641]
    p-6 rounded-2xl transition-all duration-300 hover:border-primary/50 hover:shadow-[0_0_20px_-5px_rgba(6,162,194,0.2)]">
        <div class="absolute -top-4 -right-4 bg-primary p-3 rounded-xl shadow-lg
        transition-transform group-hover:rotate-12 ">
            <Award class="text-white" :size="24"/>
        </div>
        <div class="flex items-center gap-4 mb-4 text-xs text-gray-400 ">
            <span class="flex items-center gap-1">
                <ShieldCheck :size="14" class="text-primary"/>
                {{ cert.issuer }}
            </span>
        </div>
        <h3 class="text-xl font-bold mb-3 group-hover:text-primary transition-colors">
            {{ cert.title }}
        </h3>
        <p class="text-gray-400 text-sm mb-6 line-clamp-2">
            {{ cert.desc }}
        </p>
        <a href="cert.link"
        target="_blank"
        rel="noopener noreferrer"
        class="inline-flex items-center gap-2 text-sm font-medium text-primary hover:text-white transition-colors border-b border-transparent hover:border-white pb-1">
        View Certificate <ExternalLink :size="14"/> </a>

        
    </div>
</template>