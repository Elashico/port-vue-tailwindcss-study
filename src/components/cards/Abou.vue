<script setup>

defineProps({
    stat: {
        type: Object,
        required: true
    }
})

</script>
<template>
    <div class="text-center rounded-2xl bg-[#111a3e] border border-[#1f1641] 
    p-5 transition-all duration-300 hover:border-b-green-600">
        <h3 class="text-primary font-bold text-2xl md:text-3xl">
            {{stat.value }}
        </h3>
        <p class="text-xs text-gray-400 uppercase tracking-wider mt-1">
            {{ stat.label }}
        </p>
    </div>
</template>