<template>
    <Head title="Home" />

    <CustomerLayout>
        <div class="pt-[14%] sm:pt-[12%] md:pt-[12%] lg:pt-[6%] mx-auto">
            <div class="container">
                <!-- banner -->
                <section class="grid md:grid-cols-5 gap-8 items-center">
                    <div class="col-span-3">
                        <img
                            src="/assets/banner-home.png"
                            class="md:hidden w-[200px] object-cover mx-auto my-8"
                            alt=""
                        />
                        <h1
                            class="font-semibold text-4xl xl:text-5xl leading-[3rem] xl:leading-[3.875rem]"
                        >
                           Découvrez l’avenir numérique en innovant.
                        </h1>
                        <p class="mb-10 mt-8 md:mb-12 md:mt-14">
                           Avec Under, tout le monde peut gagner des roupies
                            d'abord en ligne. Commencez par ce que vous êtes
                            savoir, voir ce qui fonctionne et l'obtenir
                            paiement. C'est si simple.
                        </p>
                        <Link
                            :href="route('dashboard')"
                            class="bg-primary text-white py-3 px-16 rounded-full font-semibold hover:shadow-lg"
                            >Commencer à vendre</Link
                        >
                    </div>
                    <div class="col-span-2">
                        <img
                            src="/assets/banner-home.png"
                            class="hidden md:block w-full h-full object-cover"
                            alt=""
                        />
                    </div>
                </section>
                <!-- end banner -->

                <!-- about -->
                <section class="my-[3rem] md:my-[6.25rem]">
                    <div class="text-end">
                        <h1 class="font-semibold text-[2rem] mb-5">
                            Vendre n'importe quoi
                        </h1>
                    </div>
                    <div class="grid md:grid-cols-2 gap-8">
                        <div class="hidden md:block md:row-span-1">
                            <img
                                src="/assets/about.png"
                                class="w-full h-[20rem] rounded-[1.25rem] object-cover"
                                alt=""
                            />
                        </div>
                        <div class="md:row-span-1">
                            <p class="mb-2 md:mb-5">
                                Logiciel. Leçon vidéo. Albums de chansons. Peu importe!
                                Diger a été créé pour vous aider à expérimenter
                                avec toutes sortes d'idées et de formats.
                            </p>
                            <div class="ms-4">
                                <div
                                    v-for="(value, key) in advantages"
                                    :key="key"
                                    class="flex gap-3 items-center mb-[.62rem]"
                                >
                                    <img src="/assets/icon/ul.svg" alt="" />
                                    <p>{{ value }}</p>
                                </div>
                            </div>
                            <p class="mb-2 md:mb-5">
                               C'est sérieux, on peut tout vendre !
                            </p>
                        </div>
                    </div>
                </section>
                <!-- end about -->

                <!-- product by category -->
                <section class="mb-[6.25rem]">
                    <div class="text-center mb-[1.875rem]">
                        <h1
                            class="font-semibold text-2xl xl:text-[2rem] mx-auto mb-4"
                        >
                           Vous cherchez de l’inspiration sur ce que vous pouvez vendre ?
                        </h1>
                        <p class="font-medium text-xl xl:text-2xl">
                            Découvrez les produits et créateurs les plus vendus sur Diger
                        </p>
                    </div>
                    <div class="grid grid-cols-1 lg:grid-cols-2 gap-5">
                        <div v-for="(value, index) in category" :key="index">
                            <Link :href="route('productByCategory', value.id)">
                                <div
                                    class="bg-white rounded-[1.25rem] p-[.62rem] box_category flex gap-6"
                                >
                                    <img
                                        :src="'/assets/' + value.image"
                                        class="h-full w-32 rounded-2xl object-cover"
                                        :alt="value.name"
                                    />
                                    <div class="mt-[3%]">
                                        <h1
                                            class="text-xl font-semibold mb-[.6rem]"
                                        >
                                            {{ value.name }}
                                        </h1>
                                        <p class="font-medium mb-[.38rem]">
                                            {{ value.description }}
                                        </p>
                                        <!-- <div
                                            class="flex gap-2 items-center mb-1"
                                        >
                                            <img
                                                src="/assets/icon/user-solid.svg"
                                                alt=""
                                            />
                                            <p class="text-sm">
                                                21839 Pencipta
                                            </p>
                                        </div>
                                        <div class="flex gap-2 items-center">
                                            <img
                                                src="/assets/icon/boxes.svg"
                                                alt=""
                                            />
                                            <p class="text-sm">
                                                9813847 Produk Digital
                                            </p>
                                        </div> -->
                                    </div>
                                </div>
                            </Link>
                        </div>
                    </div>
                </section>
                <!-- end product by category -->

                <!-- slogan -->
                <section class="my-[6.25rem]">
                    <div class="box_slogan py-12">
                        <h1
                            class="text-center text-white text-2xl xl:text-[2rem] font-semibold md:w-4/5 mx-auto"
                        >
                           Partagez vos produits numériques. <br />
                           Quelqu’un en a besoin.
                        </h1>
                        <div class="mt-4 text-center">
                            <Link
                                :href="route('dashboard')"
                                class="block w-max mx-auto bg-white text-primary py-2.5 px-14 border border-primary rounded-full font-semibold hover:shadow-lg"
                                >Commencer à vendre</Link
                            >
                        </div>
                    </div>
                </section>
                <!-- end slogan -->
            </div>
        </div>
    </CustomerLayout>
</template>

<script setup>
import { Head, Link, usePage } from "@inertiajs/vue3";
import CustomerLayout from "@/Layouts/CustomerLayout.vue";
import { ref } from "vue";

const advantages = ref([
    "Vendez votre liste Top 10",
    "Vendez vos astuces crypto",
    "Vendez vos packages fractals",
    "Vendez votre livre de recettes céto",
    "Vendez vos scènes C4D",
    "Vendez votre nouvel emoji",
]);
const { props } = usePage();
const category = ref(props.categories);
</script>

<style scoped>
.container {
    max-width: 1180px;
}
/* product by category */
.box_category {
    box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.1);
    min-height: 9.875rem;
    max-height: fit-content;
}
/* end product by category */

/* slogan */
.box_slogan {
    border-radius: 1.25rem;
    background: linear-gradient(
        134deg,
        #feb20e 0%,
        rgba(254, 178, 14, 0.5) 100%
    );
    box-shadow: 0px 0px 6px 0px rgba(0, 0, 0, 0.1);
}
/* end slogan */
</style>
