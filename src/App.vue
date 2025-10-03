<script setup>
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import ContactSection from './components/ContactSection.vue'
import ProductsSection from './components/ProductsSection.vue'
import NavBar from './components/NavBar.vue'
</script>

<template>
    <main class="bg-zinc-100 min-h-screen font-kanit">
        <NavBar /><HeroSection /><ProductsSection /><AboutSection /><ContactSection />
    </main>
    <div class="fixed bottom-2 right-2 bg-black text-white text-xs px-2 py-1 rounded z-[9999]">
        <span class="block sm:hidden">default (&lt;640px)</span>
        <span class="hidden sm:block md:hidden">sm (≥640px)</span>
        <span class="hidden md:block lg:hidden">md (≥768px)</span>
        <span class="hidden lg:block xl:hidden">lg (≥1024px)</span>
        <span class="hidden xl:block 2xl:hidden">xl (≥1280px)</span>
        <span class="hidden 2xl:block">2xl (≥1536px)</span>
    </div>
</template>

<style scoped></style>
