<script setup>
import { onMounted } from 'vue'

onMounted(() => {
    const observer = new IntersectionObserver(
        (entries) => {
            entries.forEach((entry) => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('show')
                } else {
                    entry.target.classList.remove('show')
                }
            })
        },
        { threshold: 0.1 },
    )

    document.querySelectorAll('.fade-in').forEach((el) => observer.observe(el))
})
</script>

<template>
    <section id="About" class="fade-in main-bg min-h-[400px] w-full center text-black secondary-bg">
        <h1>About</h1>
    </section>
</template>

<style scoped></style>
