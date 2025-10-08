<script setup>
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import ContactSection from './components/ContactSection.vue'
import ProductsSection from './components/ProductsSection.vue'
import NavBar from './components/NavBar.vue'
</script>

<template>
    <main class="main-bg min-h-screen font-kanit">
        <NavBar /><HeroSection /><ProductsSection /><AboutSection /><ContactSection />
    </main>
</template>

<style scoped></style>
