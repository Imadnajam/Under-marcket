<script setup>
import Logo from "@/Components/Logo.vue";
import { Link } from "@inertiajs/vue3";
</script>

<template>
    <footer class="container mt-10">
        <!-- Logo -->
        <div
            class="flex justify-between items-center bg-white border-t border-gray-100 py-3"
        >
            <Link :href="route('dashboard')">
                <Logo class="block h-9 w-auto fill-current text-gray-800" />
            </Link>
            <p class="text-sm font-medium text-[#555]">
                &#169; {{ new Date().getFullYear() }} Under. NJ
            </p>
        </div>
    </footer>
</template>
