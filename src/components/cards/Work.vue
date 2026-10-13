<script setup>
import { Briefcase, Building2, Calendar } from 'lucide-vue-next';


defineProps({
    exp: {
        type: Object,
        required: true
    }
})

</script>

<template>
    <div class="group relative p-6 rounded-2xl bg-[#111a3e] border border-[#1f1641]
     hover:border-green-200/50 transition-all duration-300">
        <div class="flex gap-4">
            <div class="shrink-0 mt-1">
                <div class="p-3 bg-[#050816] rounded-xl border border-gray-800
                 group-hover:border-green-200/50 transition-colors">
                    <Briefcase class="text-primary" :size="24"/>
                </div>
            </div>
            <div class="grow">
                <h3 class="text-xl font-bold text-white group-hover:text-green-200 transition-colors">
                    {{ exp.role }}</h3>
                <div class="flex flex-col sm:flex-row sm:item-center gap-2 sm:gap-4 text-sm text-gray-400">
                    <span class="flex items-center gap-1.5">
                        <Building2 :size="14" class="text-primary"/>
                        {{ exp.company }}
                    </span>
                    <span class="flex items-center gap-1.5">
                        <Calendar :size="14" class="text-primary"/>
                        {{ exp.date }}
                    </span>

                </div>
            </div>

        </div>
        
    </div>
</template>
