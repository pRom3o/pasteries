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
        class="fade-in main-bg min-h-[300px] w-full flex flex-col items-center gap-5 p-6 text-black"
    >
        <h1 class="items-start text-5xl text-secondary">Our Products</h1>
        <div class="center w-[60%] p-6">
            <div class="grid grid-cols-3 w-full gap-3 text-center space-y-5">
                <div
                    class="fade-in delay-1 flex flex-col items-center justify-between h-[300px] w-[200px] rounded-2xl shadow prod-bg text-prod"
                >
                    <img
                        src="../assets/Images/item-1.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] p-2 flex flex-col items-start justify-center">
                        <p>Coconut Doughuts</p>
                        <p>$2 per piece</p>
                    </div>
                </div>
                <div
                    class="fade-in delay-1 flex flex-col items-center justify-between h-[300px] w-[200px] rounded-2xl shadow prod-bg text-prod"
                >
                    <img
                        src="../assets/Images/item-1.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] p-2 flex flex-col items-start justify-center">
                        <p>Coconut Doughuts</p>
                        <p>$2 per piece</p>
                    </div>
                </div>
                <div
                    class="fade-in delay-1 flex flex-col items-center justify-between h-[300px] w-[200px] rounded-2xl shadow prod-bg text-prod"
                >
                    <img
                        src="../assets/Images/item-1.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] p-2 flex flex-col items-start justify-center">
                        <p>Coconut Doughuts</p>
                        <p>$2 per piece</p>
                    </div>
                </div>
                <div
                    class="fade-in delay-3 flex flex-col items-center justify-between h-[300px] w-[200px] rounded-2xl shadow prod-bg text-prod"
                >
                    <img
                        src="../assets/Images/item-1.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] p-2 flex flex-col items-start justify-center">
                        <p>Coconut Doughuts</p>
                        <p>$2 per piece</p>
                    </div>
                </div>
                <div
                    class="fade-in delay-3 flex flex-col items-center justify-between h-[300px] w-[200px] rounded-2xl shadow prod-bg text-prod"
                >
                    <img
                        src="../assets/Images/item-1.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] p-2 flex flex-col items-start justify-center">
                        <p>Coconut Doughuts</p>
                        <p>$2 per piece</p>
                    </div>
                </div>
                <div
                    class="fade-in delay-3 flex flex-col items-center justify-between h-[300px] w-[200px] rounded-2xl shadow secondary-bg prod-bg text-prod"
                >
                    <img
                        src="../assets/Images/item-1.jpg"
                        alt=""
                        class="h-[80%] rounded-t-2xl w-full"
                    />
                    <div class="w-full h-[20%] p-2 flex flex-col items-start justify-center">
                        <p>Coconut Doughuts</p>
                        <p>$2 per piece</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped></style>
