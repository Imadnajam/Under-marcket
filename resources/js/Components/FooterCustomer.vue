<template>
    <footer class="container">
        <div class="border-t border-gray-100 pt-6 pb-8">
            <!-- Logo -->
            <Link :href="route('home')">
                <ApplicationLogo />
            </Link>
            <div
                class="grid md:grid-cols-5 gap-40 justify-between items-center"
            >
                <div class="md:col-span-4 lg:col-span-3">
                    <p class="my-6 font-semibold text-xl">
                       La Plateforme Ultime pour Vendre Vos Produits Numériques
                    </p>

                    <p class="text-sm font-medium text-[#555] mt-12">
                        &#169; {{ new Date().getFullYear() }} Under. NJ
                    </p>
                </div>
                <div
                    class="hidden md:block md:col-span-1 lg:col-span-2 justify-self-end"
                >
                    <div class="flex md:flex-col lg:flex-row gap-5">
                        <a
                            v-for="(value, key) in medsoc"
                            :key="key"
                            :href="value.link"
                            target="_blank"
                            ><img
                                :src="value.image"
                                alt="value.name"
                                class="hover-img h-8"
                        /></a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script setup>
import ApplicationLogo from "@/Components/ApplicationLogo.vue";
import { Link } from "@inertiajs/vue3";
import { ref } from "vue";

const medsoc = ref([
    {
        image: "/assets/icon/LinkedIn.svg",
        name: "Instagram",
        link: "https://www.linkedin.com/",
    },
    {
        image: "/assets/icon/github.svg",
        name: "Instagram",
        link: "https://www.github.com/",
    },
    {
        image: "/assets/icon/instagram.svg",
        name: "Instagram",
        link: "https://www.instagram.com/",
    },
    {
        image: "/assets/icon/twitter.svg",
        name: "Instagram",
        link: "https://www.twitter.com/",
    },
]);
</script>

<style scoped>
.hover-img:hover {
    filter: invert(78%) sepia(19%) saturate(5932%) hue-rotate(350deg)
        brightness(106%) contrast(102%) !important;
}
</style>
