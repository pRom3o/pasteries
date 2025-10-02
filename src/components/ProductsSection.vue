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
        id="Products"
        class="fade-in secondary-bg min-h-[300px] w-full col-center gap-5 p-6 text-black"
    >
        <h1 class="text-5xl text-secondary">Our Products</h1>
        <div class="col-center w-full xl:w-[65%] p-6 h-full">
            <h2 class="text-3xl text-secondary mb-5">Doughuts</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 w-full gap-5 space-y-5">
                <div
                    class="fade-in delay-1 flex flex-col items-center justify-between h-[300px] w-full rounded-2xl shadow item-bg text-prod"
                >
                    <img
                        src="../assets/Images/item-1.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] py-8 px-2 flex flex-col items-start justify-center">
                        <p class="font-semibold text-lg font-body">Chocolate doughuts</p>
                        <p>₦1200 per piece</p>
                    </div>
                </div>
                <div
                    class="fade-in delay-1 flex flex-col items-center justify-between h-[300px] w-full rounded-2xl shadow item-bg text-prod"
                >
                    <img
                        src="../assets/Images/item-7.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] py-4 px-2 flex flex-col items-start justify-center">
                        <p class="font-semibold text-lg font-body">Milky doughuts</p>
                        <p>₦1500 per piece</p>
                    </div>
                </div>
                <div
                    class="fade-in delay-1 flex flex-col items-center justify-between h-[300px] w-full rounded-2xl shadow item-bg text-prod"
                >
                    <img
                        src="../assets/Images/item-8.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] py-4 px-2 flex flex-col items-start justify-center">
                        <p class="font-semibold text-lg font-body">Powdered sugar doughuts</p>
                        <p>₦800 per piece</p>
                    </div>
                </div>
                <div
                    class="fade-in delay-1 flex flex-col items-center justify-between h-[300px] w-full rounded-2xl shadow item-bg text-prod"
                >
                    <img
                        src="../assets/Images/jam-doughnuts.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] py-4 px-2 flex flex-col items-start justify-center">
                        <p class="font-semibold text-lg font-body">Jam doughuts</p>
                        <p>₦1200 per piece</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped></style>
