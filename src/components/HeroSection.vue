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
    <section
        id="Home"
        class="min-h-screen w-full center relative bg-center bg-cover"
        style="background-image: url('src/assets/Images/pasteries-hero.jpg')"
    >
        <div class="absolute inset-0 bg-black opacity-40"></div>
        <div class="h-full w-full text-center col-center z-10 leading-10 text-primary">
            <h1 class="heading text-6xl lg:text-9xl fade-in">Celine's Treats</h1>
            <h2 class="heading text-4xl md:text-6xl lg:text-7xl fade-in delay-1">
                Delicious Pasteries
            </h2>
            <p class="fade-in delay-1 body-text lg:text-xl mt-2 text-secondary px-3">
                <i>Turning simple beginings into timeless flavors, one pastry at a time</i>
            </p>
            <button
                class="px-8 py-2 rounded-2xl fade-in delay-3 font-body center gap-4 font-semibold bg-[#c3ae92] text-black opacity-40 mt-5 hover:bg-[#f0e5d7] hover"
            >
                Order Now
                <span
                    ><svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="16"
                        height="16"
                        fill="currentColor"
                        class="bi bi-arrow-right"
                        viewBox="0 0 16 16"
                    >
                        <path
                            fill-rule="evenodd"
                            d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8"
                        /></svg
                ></span>
            </button>
        </div>
    </section>
</template>

<style scoped>
.hover {
    transition: all 0.3s ease-in-out;
}
</style>
