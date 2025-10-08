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
        class="fade-in min-h-[350px] w-full flex flex-col items-center gap-6 p-4 bg-[#dcdcdc]"
    >
        <h1 class="items-start text-5xl lg:text-6xl py-4 fade-in">About Celine's treats</h1>
        <div
            class="flex lg:flex-row flex-col items-center justify-evenly space-y-8 w-full lg:w-[80%] xl:w-[60%] p-4 h-full"
        >
            <div
                class="h-full flex justify-center md:w-[40%] lg:w-1/2 transition-transform duration-500 ease-in-out transform hover:scale-105"
            >
                <div
                    class="h-80 w-80 border rounded-full bg-cover bg-center"
                    style="background-image: url('src/assets/Images/about-2.jpg')"
                ></div>
            </div>
            <div class="w-full lg:w-1/2 font-heading text-xl slide-in-right">
                <p class="text-[12px] md:text-lg">
                    <strong class="text-4xl pr-2">“</strong>I never actually planned on starting a
                    business. Most times when I get an idea, I focus too much on the big picture —
                    the finished product I imagine. That often made me stall, and many of my ideas
                    ended up being set aside, but this time was different. When the idea for
                    Celine’s Treats came, I realized that big things happen when you’re bold enough
                    to start small. So here I am. I’ve always been passionate about pastries and
                    food. In a world where so many things come and go, food remains — it brings
                    comfort, joy, and connection. For me, pastries are more than just desserts;
                    they’re little pieces of happiness, and through Celine’s Treats, I want to share
                    that happiness with as many people as possible.<strong class="text-4xl pl-1"
                        >”</strong
                    >
                </p>
            </div>
        </div>
    </section>
</template>

<style scoped>
/* p {
    color: #3b543b;
} */

.slide-in-left {
    opacity: 0;
    transform: translateY(-50px); /* negative for left */
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
    transform: translateY(50px); /* positive for right */
    transition:
        opacity 0.8s ease-out,
        transform 0.8s ease-out;
}

.slide-in-right.show {
    opacity: 1;
    transform: translateX(0);
}
</style>
