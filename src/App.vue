<script setup>
import Header from './components/Header.vue'
import HeroSection from './components/HeroSection.vue';
import EducationII from './components/EducationII.vue';
import Certificates from './components/Certificates.vue';
import AboutSection from './components/AboutSection.vue';
import Experience from './components/Experience.vue';
import Projects from './components/Projects.vue';
import Contacts from './components/ContactSection.vue'
import Footer from './components/Footer.vue'

import AOS from 'aos';
import 'aos/dist/aos.css';
import { onMounted } from 'vue';


onMounted(() => {
  AOS.init({
    duration: 1000, // Animation duration in milliseconds
    once: false, // Whether animation should happen only once
    offset:100,
  });
});
</script>

<template>
  <div class="bg-[#111827] min-h-screen">
    <Header />
    <HeroSection />
    <EducationII />
    <Certificates />
    <AboutSection />
    <Experience />
    <Projects />
    <Contacts />
    <Footer />
  </div>
</template>