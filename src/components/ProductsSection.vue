<script setup>
import { onMounted } from 'vue'
import pasteries from '@/data/pasteries.json'
import { ref } from 'vue'
import { computed } from 'vue'

const categories = ['Cakes', 'Doughnuts', 'Others']

const selectedCategory = ref('Cakes')

const items = computed(() => pasteries[selectedCategory.value])

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

// transition-transform duration-500 ease-in-out transform hover:scale-105
</script>

<template>
    <section
        id="Products"
        class="fade-in secondary-bg min-h-[300px] w-full col-center gap-5 p-6 text-black"
    >
        <h1 class="text-5xl text-secondary">Our Products</h1>

        <div class="flex gap-4 mb-6">
            <button
                v-for="category in categories"
                :key="category"
                @click="selectedCategory = category"
                class="px-4 py-2 rounded bg-pink-800"
            >
                {{ category }}
            </button>
        </div>
        <div class="col-center w-full xl:w-[65%] p-6 h-full">
            <h2 class="text-3xl text-secondary mb-5">{{ selectedCategory }}</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 w-full gap-5 space-y-5">
                <div
                    class="primary-bg fade-in flex flex-col items-center justify-between h-[300px] w-full rounded-2xl shadow text-prod"
                    v-for="item in items"
                    :key="item.id"
                >
                    <img :src="item.img" :alt="item.name" class="h-[80%] rounded-t-2xl w-full" />
                    <div class="w-full h-[20%] py-8 px-2 flex flex-col items-start justify-center">
                        <p class="font-semibold text-lg font-body">{{ item.name }}</p>
                        <p>{{ item.price }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped></style>
