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

    document
        .querySelectorAll('.fade-in, .slide-in-right, .slide-in-left')
        .forEach((el) => observer.observe(el))
})
</script>

<template>
    <section
        id="About"
        class="fade-in primary-bg min-h-[350px] w-full flex flex-col items-center gap-6 p-4 text-black"
    >
        <h1 class="items-start text-5xl py-4 fade-in">About Celine's treats</h1>
        <div class="flex items-center justify-evenly w-[80%] p-4 h-full">
            <div
                class="h-full flex justify-center w-1/2 slide-in-left transition-transform duration-500 ease-in-out transform hover:scale-105"
            >
                <div class="h-40 w-40 border"></div>
            </div>
            <div class="w-1/2 font-heading text-xl slide-in-right">
                <p>
                    “I never actually planned on starting a business. Most times when I get an idea,
                    I focus too much on the big picture — the finished product I imagine. That often
                    made me stall, and many of my ideas ended up being set aside. But this time was
                    different. When the idea for Celine’s Treats came, I realized that big things
                    happen when you’re bold enough to start small. So here I am. I’ve always been
                    passionate about pastries and food. In a world where so many things come and go,
                    food remains — it brings comfort, joy, and connection. For me, pastries are more
                    than just desserts; they’re little pieces of happiness. And through Celine’s
                    Treats, I want to share that happiness with as many people as possible.”
                </p>
            </div>
        </div>
    </section>
</template>

<style scoped>
.slide-in-left {
    opacity: 0;
    transform: translateX(-100px); /* negative for left */
    transition:
        opacity 0.8s ease-out,
        transform 0.8s ease-out;
}

.slide-in-left.show {
    opacity: 1;
    transform: translateX(0);
}

.slide-in-right {
    opacity: 0;
    transform: translateX(100px); /* positive for right */
    transition:
        opacity 0.8s ease-out,
        transform 0.8s ease-out;
}

.slide-in-right.show {
    opacity: 1;
    transform: translateX(0);
}
</style>
