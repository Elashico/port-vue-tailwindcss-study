<script setup>

defineProps({
    skil: {
        type: Object,
        required: true
    }
})

</script>

<template>
    <div class="group">
        <div class="flex items-center justify-between mb-2">
            <div class="flex items-center gap-3">
                <div class="p-2 bg-[#111a3e] rounded-lg group-hover:bg-primary transition-colors duration-300">
                    <component 
                    :is="skil.icons"
                    :size="20"
                    class="text-primary group-hover:text-white"
                    />
                </div>
                <span class="font-medium tracking-wide">{{ skil.name }}</span>
            </div>
            <span class="text-primary font-bold">
                {{ skil.width }}
            </span>    
        </div>
        
        <div class="h-2 w-full bg-[#131d30] rounded-full p-0.5">
            <div class="h-full rounded-full bg-linear-to-r from-primary to-green-200 shadow-[0_0_10px_#06a2c2]"
            :style="{width: skil.width}">
            </div>   
        </div>

    </div>
</template>