<script setup></script>

<template>
    <div
        class="w-full fixed top-0 min-h-10 shadow font-semibold flex items-center justify-evenly md:px-5 py-3 md:gap-6 z-55 backdrop-blur-md"
    >
        <img
            src="../assets/Images/header.jpg"
            alt="Celine's Treats"
            class="h-10 w-10 rounded-full"
        />
        <ul class="flex gap-6">
            <li class="px-4 py-2"><a href="#Home">Home</a></li>
            <li class="px-4 py-2"><a href="#Products">Products</a></li>
            <li class="px-4 py-2"><a href="#About">About</a></li>
            <li class="px-4 py-2"><a href="#Contact">Contact</a></li>
        </ul>
        <p>Support</p>
    </div>
</template>

<style scoped>
.bg {
    opacity: 0.5;
}

a,
p {
    font-weight: 400;
}
</style>
