<script setup>
import { GraduationCap, Calendar, CheckCircle2 } from 'lucide-vue-next'

defineProps({
    edu: {
        type: Object,
        required: true
    }
})
</script>

<template>
    <div class="relative group p-6 rounded-2xl bg-[#1f1641] border border-transparent transition-all duration-300
        hover:border-b-green-700 hover:-translate-y-1">
        <!-- Top Section -->
        <div class="flex flex-col sm:flex-row sm:items-center
                    justify-between gap-5 mb-4">

            <div class="flex items-center gap-3">
                <div
                    class="p-2 bg-[#050816] rounded-lg border border-primary/20 transition-colors
                    group-hover:border-primary "
                >
                    <GraduationCap class="text-primary" :size="24" />
                </div>

                <div>
                    <h3
                    class="text-lg font-bold text-white
                    group-hover:text-primary transition-colors"
                    >
                        {{ edu.degree }}
                    </h3>

                    <p class="text-gray-400 text-sm">
                        {{ edu.institution }}
                    </p>
                </div>
            </div>

            <div
            class="flex items-center gap-2 text-xs font-medium
            bg-[#050816] px-3 py-1 rounded-full border border-gray-700
            w-fit whitespace-nowrap"
            >
                <Calendar :size="12" class="text-primary" />
                {{ edu.duration }}
            </div>
        </div>

        <!-- Details -->
        <p class="text-gray-400 text-sm leading-relaxed mb-4">
            {{ edu.details }}
        </p>

        <!-- Optional academic excellence badge -->
        <div
        v-if="edu.academic_excellence"
        class="flex items-center gap-2 text-[10px] uppercase
        tracking-wider text-primary font-bold">
            <CheckCircle2 :size="12" />
            <span>Academic Excellence</span>
        </div>
    </div>
</template>