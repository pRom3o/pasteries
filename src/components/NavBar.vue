<template>
    <div
        class="w-full fixed top-0 min-h-10 shadow font-semibold flex items-center md:justify-evenly justify-between px-5 py-3 md:gap-6 z-55 secondary-bg"
    >
        <img src="/Images/header.jpg" alt="Celine's Treats" class="h-10 w-10 rounded-full" />
        <nav class="flex md:gap-6">
            <li class="px-4 py-2 hover:rounded-2xl hover hover:bg-[#D3D3D3] hover:text-[#333333]">
                <a href="#Home">Home</a>
            </li>
            <li class="px-4 py-2 hover:rounded-2xl hover hover:bg-[#D3D3D3] hover:text-[#333333]">
                <a href="#Products">Products</a>
            </li>
            <li class="px-4 py-2 hover:rounded-2xl hover hover:bg-[#D3D3D3] hover:text-[#333333]">
                <a href="#About">About</a>
            </li>
            <li class="px-4 py-2 hover:rounded-2xl hover hover:bg-[#D3D3D3] hover:text-[#333333]">
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
