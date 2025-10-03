<script setup>
import { ref, onMounted } from 'vue'
const activeSection = ref('Home')

onMounted(() => {
    const sections = document.querySelectorAll('section') // each section should have id="Home", id="Products", etc.

    const observer = new IntersectionObserver(
        (entries) => {
            entries.forEach((entry) => {
                if (entry.isIntersecting) {
                    activeSection.value = entry.target.id
                }
            })
        },
        { threshold: 0.6 }, // 60% of section visible
    )

    sections.forEach((section) => observer.observe(section))
})
</script>

<template>
    <div
        class="w-full fixed top-0 min-h-10 shadow font-semibold flex items-center md:justify-evenly justify-between px-5 py-3 md:gap-6 z-55 primary-bg"
    >
        <img
            src="../assets/Images/header.jpg"
            alt="Celine's Treats"
            class="h-10 w-10 rounded-full"
        />
        <nav class="flex md:gap-6">
            <li class="px-4 py-2 hover:bg-[#ddd9d4] hover:rounded-2xl hover">
                <a href="#Home">Home</a>
            </li>
            <li class="px-4 py-2 hover:bg-[#ddd9d4] hover:rounded-2xl hover">
                <a href="#Products">Products</a>
            </li>
            <li class="px-4 py-2 hover:bg-[#ddd9d4] hover:rounded-2xl hover">
                <a href="#About">About</a>
            </li>
            <li class="px-4 py-2 hover:bg-[#ddd9d4] hover:rounded-2xl hover">
                <a href="#Contact">Contact</a>
            </li>
        </nav>
        <p><a href="#Contact" class="md:flex hidden">Support</a></p>
    </div>
</template>

<style scoped>
.hover {
    transition: all 0.3s ease-in-out;
}

a,
p {
    font-weight: 400;
}

li {
    list-style: none;
}
</style>
