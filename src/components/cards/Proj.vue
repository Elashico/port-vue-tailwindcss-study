<script setup>

defineProps({
    project: {
        type: Object,
        required: true
    }
})

</script>

<template>
    <div data-aos="fade-up">
        <div class="group bg-gray-800 rounded-lg overflow-hidden shadow-sm hover:shadow-lg hover:scale-105
        transition-all duration-300">
            <img 
            :src="project.image" 
            :alt="project.title"
            class="w-full h-44 object-cover hover:opacity-90 transition-opacity duration-300">
            <div class="p-4">
                <h3 class="text-lg font-semibold text-white group-hover:text-green-400 transition-colors">
                    {{ project.title }}
                </h3>
                <p class="text-sm text-gray-400 mt-1">
                    {{ project.desc }}
                </p>
                <div class="flex flex-wrap gap-1.5 mt-3">
                    <span
                    v-for="(tech,idx) in project.techg"
                    :key="idx"
                    class="text-xs px-2 py-0.5 bg-gray-500 text-gray-300 rounded hover:bg-green-400 
                    transition-colors hover:text-white duration-300">
                    {{ tech }}
                    </span>
                </div>

            </div>
        </div>
    </div> 
</template>