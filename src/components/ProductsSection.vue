<script setup>
import { onMounted } from 'vue'
import pasteries from '@/data/pasteries.json'
import { ref } from 'vue'
import { computed } from 'vue'

const categories = ['Cakes', 'Doughnuts', 'Others']

const selectedCategory = ref('Cakes')

const items = computed(() => {
    return pasteries[selectedCategory.value] || []
})

onMounted(() => {
    console.log(items.value)
})
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
    <section id="Products" class="fade-in min-h-[200px] col-center gap-5 p-6 secondary-bg">
        <h1 class="md:text-6xl font-medium text-3xl">Delights we offer</h1>
        <div class="flex gap-4 mb-4">
            <button
                v-for="category in categories"
                :key="category"
                @click="selectedCategory = category"
                class="px-4 py-2 rounded-xl shadow-md border border-gray-400 hover"
                :class="[
                    selectedCategory === category
                        ? ' bg-[#333333] text-[#D3D3D3]'
                        : 'bg-[#D3D3D3] text-[#333333] hover:bg-[#333333] hover:text-[#D3D3D3]',
                ]"
            >
                {{ category }}
            </button>
        </div>

        <div class="min-h-[200px] col-center rounded-2xl w-full secondary-bg">
            <div class="col-center w-full md:w-[95%] xl:w-[80%] 2xl:w-[70%] h-full">
                <div
                    class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-4 md:w-full gap-5 space-y-5"
                >
                    <div
                        class="fade-in flex flex-col items-center justify-between h-[300px] w-full rounded-2xl shadow bg-[#e1e1e1]"
                        v-for="item in items"
                        :key="item.id"
                    >
                        <img
                            :src="item.img"
                            :alt="item.name"
                            class="h-[80%] rounded-t-2xl w-full"
                        />
                        <div
                            class="w-full h-[20%] py-8 px-2 flex flex-col items-start justify-center"
                        >
                            <p class="font-semibold text-lg font-body">{{ item.name }}</p>
                            <p>{{ item.price }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.hover {
    transition: all 0.3s ease-in-out;
}

.div {
    box-shadow: 1px 1px 30px rgba(0, 0, 0, 0.1);
}
</style>
