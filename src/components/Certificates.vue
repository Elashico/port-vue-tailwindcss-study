<script setup>
import Cert from './cards/Cert.vue'

const certifications = [
    {
        id: 1,
        title: 'Meta Front-End Developer Professional Certificate',
        issuer: 'Coursera / Meta',
        date: 'Dec 2023',
        link: "#",
        desc: 'Officia aliquip aute magna enim. Id esse consectetur magna aute. Adipisicing proident esse eiusmod velit fugiat eu velit. Ut exercitation elit ipsum aliquip.'
    },
    {
        id: 2,
        title: 'Meta Front-End Developer Professional Certificate',
        issuer: 'Coursera / Meta',
        date: 'Dec 2023',
        link: "#",
        desc: 'Officia aliquip aute magna enim. Id esse consectetur magna aute. Adipisicing proident esse eiusmod velit fugiat eu velit. Ut exercitation elit ipsum aliquip.'
    },
    {
        id: 3,
        title: 'Meta Front-End Developer Professional Certificate',
        issuer: 'Coursera / Meta',
        date: 'Dec 2023',
        link: "#",
        desc: 'Officia aliquip aute magna enim. Id esse consectetur magna aute. Adipisicing proident esse eiusmod velit fugiat eu velit. Ut exercitation elit ipsum aliquip.'
    }
]

</script>
<template>
    <section class="text-white py-10 px-6 lg:px-[14vw]" id="certificates">
        <div class="mb-16">
            <p class="text-primary text-sm uppercase mb-2 tracking-widest font-semibold">
                Achievements
            </p>
            <h2 class="text-4xl md:text-5xl font-bold text-white">
                Certifications.
            </h2>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            <Cert
                v-for="cert in certifications"
                :key="cert.id"
                :cert="cert"/>
        </div>
    </section>
</template>
