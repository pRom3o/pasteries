<script setup>
import emailjs from '@emailjs/browser'
import { onMounted, ref } from 'vue'
import LoadingIcon from '../../public/icons/LoadingIcon.vue'

const form = ref(null)
const failed = ref(false)
const success = ref(false)
const loading = ref(false)

const sendEmail = () => {
    loading.value = true
    setTimeout(() => {
        emailjs
            .sendForm(
                import.meta.env.VITE_SERVICE_ID,
                import.meta.env.VITE_TEMPLATE_ID,
                form.value,
                import.meta.env.VITE_PUBLIC_KEY,
            )
            .then(
                (response) => {
                    console.log(response.text, response.status)
                    loading.value = false
                    success.value = true
                    form.value.reset()
                },
                (error) => {
                    console.log('Failed', error)
                    failed.value = true
                },
            )
    }, 300)
    success.value = false
}

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
    <section id="Contact" class="fade-in min-h-[300px] w-full col-center px-5 py-8 bg-neutral-200">
        <h1 class="md:text-5xl text-3xl mb-10 font-semibold text-neutral-700">
            Want to place an order?
        </h1>

        <div
            class="h-full w-full md:w-[80%] xl:w-[80%] lg:w-full flex items-center justify-center gap-3 px-3 bg-[#f2f2f2] rounded-2xl shadow-sm"
        >
            <div class="h-[470px] w-1/2 lg:flex hidden rounded-2xl">
                <img src="../assets/Images/contact.jpg" alt="" class="rounded-2xl w-full" />
            </div>
            <div class="vertical-line lg:block hidden"></div>

            <div class="center lg:w-1/2 w-full">
                <form
                    ref="form"
                    @submit.prevent="sendEmail"
                    class="flex flex-col items-center space-y-5 w-full p-6 xl:px-10 2xl:px-20"
                >
                    <h2 class="md:text-3xl text-xl font-medium">Send us a detailed email...</h2>

                    <div class="col-center w-full space-y-5">
                        <div class="flex flex-col w-full">
                            <label for="name">Name</label
                            ><input type="text" required name="from_name" id="name" />
                        </div>

                        <div class="flex flex-col w-full">
                            <label for="userEmail">Email</label
                            ><input type="email" required name="from_email" id="userEmail" />
                        </div>

                        <div class="flex flex-col w-full">
                            <label for="message">Message</label>
                            <textarea
                                name="message"
                                required
                                id="message"
                                class="resize-none h-30"
                            ></textarea>
                        </div>
                    </div>
                    <div class="w-full flex items-center justify-end py-3 h-[12%]">
                        <button
                            class="px-8 py-2 rounded-2xl font-body center gap-4 font-semibold hover bg-[#333333] text-[#D3D3D3] hover:bg-[#D3D3D3] hover:text-[#333333] hover:border hover:border-[#333333] border border-[#D3D3D3] shadow-md"
                            v-if="success == true"
                        >
                            Sent
                        </button>
                        <button
                            class="px-8 py-2 rounded-2xl font-body center gap-4 font-semibold hover bg-[#333333] text-[#D3D3D3] hover:bg-[#D3D3D3] hover:text-[#333333] hover:border hover:border-[#333333] border border-[#D3D3D3] shadow-md"
                            v-else-if="loading == true"
                        >
                            <LoadingIcon />
                        </button>
                        <button
                            class="px-8 py-2 rounded-2xl font-body center gap-4 font-semibold hover bg-[#333333] text-[#D3D3D3] hover:bg-[#D3D3D3] hover:text-[#333333] hover:border hover:border-[#333333] border border-[#D3D3D3] shadow-md"
                            @click="submit"
                            v-else
                        >
                            Send
                        </button>
                    </div>
                    <p class="md:text-lg">Or contact us through one of our socials:</p>
                    <ul class="flex items-center justify-center gap-5 w-[30%]">
                        <li class="col-center">
                            <a
                                href="https://wa.me/+2348174700749"
                                aria-label="Chat with Celine's Treats on Whatsapp"
                                class="p-3 rounded-full bg-[#8EC09E] hover hover:bg-[#046307]"
                                ><svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    width="16"
                                    height="16"
                                    fill=""
                                    class="bi bi-whatsapp"
                                    viewBox="0 0 16 16"
                                >
                                    <path
                                        d="M13.601 2.326A7.85 7.85 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.9 7.9 0 0 0 3.79.965h.004c4.368 0 7.926-3.558 7.93-7.93A7.9 7.9 0 0 0 13.6 2.326zM7.994 14.521a6.6 6.6 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.56 6.56 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592m3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.087-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.73.73 0 0 0-.529.247c-.182.198-.691.677-.691 1.654s.71 1.916.81 2.049c.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232"
                                    /></svg
                            ></a>
                            Whatsapp
                        </li>
                        <li class="col-center">
                            <a
                                href="https://www.tiktok.com/@celinemercy229?_t=ZS-90AgHEckxmK&_r=1"
                                aria-label="Chat with Celine's Treats on Tiktok"
                                class="p-3 rounded-full bg-[#8EC09E] hover hover:bg-[#046307]"
                                ><svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    width="16"
                                    height="16"
                                    fill="black"
                                    class="bi bi-tiktok"
                                    viewBox="0 0 16 16"
                                >
                                    <path
                                        d="M9 0h1.98c.144.715.54 1.617 1.235 2.512C12.895 3.389 13.797 4 15 4v2c-1.753 0-3.07-.814-4-1.829V11a5 5 0 1 1-5-5v2a3 3 0 1 0 3 3z"
                                    /></svg
                            ></a>
                            Tiktok
                        </li>
                    </ul>
                </form>
            </div>
        </div>
    </section>
</template>

<style scoped>
.vertical-line {
    border-left: 2px solid #7e7e7e;
    height: 470px;
    border-radius: 10px;
}

label {
    color: #333333;
    font-weight: 500;
    line-height: 22 px;
}

.hover {
    transition: all 0.3s ease-in-out;
}

input,
textarea {
    border: 2px solid #032e05;
    outline: none;
    padding: 5px;
    font-weight: 400;
    border-radius: 10px;
}

input:focus,
textarea:focus {
    caret-color: #046307;
}
</style>
