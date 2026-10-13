<script setup>
import { reactive, ref } from 'vue';
import { Mail, Phone, Linkedin, MapPin } from 'lucide-vue-next';

const contactInfo = [
    {
        id: 1,
        icon: Mail,
        title: 'Email',
        value: 'sample@email.com',
        link: 'mailto:sample@email.com' 
    },
    {
        id: 2,
        icon: Phone,
        title: 'Phone',
        value: '+123 4567890',
        link: 'tel:+1234567890' 
    },
    {
        id: 3,
        icon: Linkedin,
        title: 'LinkedIn',
        value: 'linkdin.com/in/username',
        link: '#' 
    },
    {
        id: 4,
        icon: MapPin,
        title: 'Location',
        value: 'Mt. Province, Benguet',
        link: null 
    },
]

const formData = reactive({
    email: '',
    subject: '',
    message: '',
})

const isSubmitting = ref(false)

const handleSubmit = async () => {
    isSubmitting.value = true
    try{
        formData.email = ''
        formData.subject = ''
        formData.message = ''
    } catch (error) {
        alert('Failed to send mesage. Please try again')
    } finally {
        isSubmitting.value = false
    }

}
</script>

<template>
    <section class="py-20 bg-gray-900" id="contact">
        <div class="container mx-auto px-4 max-w-6xl">
            <div class="text-center mb-12">
                <h2 class="text-3xl md:text-5xl font-extrabold text-white mb-2">
                    Let's Connect.
                </h2>
                <div class="w-28 h-1 bg-primary mx-auto mt-2 round-2xl"></div>
            </div>
            <div class="grid md:grid-cols-2 gap-8">
                <div>
                    <p class="text-gray-400 m-8 leading-relaxed">
                        Sunt id nulla commodo esse Lorem nisi. Officia id eiusmod officia eiusmod eu 
                        commodo sunt qui sint dolor officia deserunt sunt esse. Consequat et qui do 
                        Lorem sunt culpa laboris adipisicing anim amet consectetur esse occaecat ad.
                    </p>
                    <div class="space-y-6">
                        <div
                        v-for="info in contactInfo"
                        :key="info.id"
                        class="flex items-center gap-4 group">
                            <!-- icon show -->
                            <div class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center 
                            group-hover:bg-green-400 transition-colors">
                            <component :is="info.icon" :size="18" class="text-primary group-hover:text-blue-950"/>
                            </div>
                            <!-- icon show -->
                            <div class="text-white font-medium text-sm">
                                <h4>
                                    {{ info.title}}
                                </h4>
                                <a 
                                v-if="info.link"
                                :href="info.link"
                                :target="info.title ==='Location' ? '_self' : '_blank'"
                                :ref="info.title === 'Location' ? '' : 'noopener noreferrer'"
                                class="text-gray-400 text-sm hover:text-green-600 transition-colors">
                                    {{ info.value }}
                                </a>
                                <p v-else class="text-gray-400 text-sm">
                                    {{ info.value}}
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- Form -->
                <div class="bg-gray-800 rounded-lg p-6">
                    <!-- Email -->
                    <form @submit.prevent="handleSubmit">
                        <div class="mb-4">
                            <label for="email"
                            class="text-white block mb-2 text-sm font-medium">
                                Email
                            </label>
                            <input type="email" id="email"
                            v-model="formData.email"
                            class="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg
                            text-white text-sm focus:outline-none focus:border-green-600 transition-colors"
                            placeholder="your@email.com" required>

                        </div>
                    </form>
                    <!-- Message -->
                     <form @submit.prevent="handleSubmit">
                        <div class="mb-6">
                            <label for="message"
                            class="text-white block mb-2 text-sm font-medium">
                                Message
                            </label>
                            <textarea  name="" id="message"
                            v-model="formData.message"
                            class="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg
                            text-white text-sm focus:outline-none focus:border-green-600 transition-colors"
                            placeholder="Tell me about your Project ...." rows="4"required>
                            </textarea>
                        </div>
                        <button
                        type="submit"
                        :disabled="isSubmitting"
                        class="w-full px-6 py-2.5 bg-primary text-white rounded-lg font-medium
                         hover:bg-green-600 transition-colors 
                         disabled:opacity-50 disabled:cursor-not-allowed ">
                        {{ isSubmitting ? 'Sending...' : 'Send Message' }}
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>
</template>