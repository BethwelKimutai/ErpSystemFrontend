<template>
    <div>
        <header>
            <nav class="bg-white border-gray-200 shadow-2xl border-yellow-500 dark:bg-gray-800">
                <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
                    <nuxt-link to="/home" class="flex items-center space-x-3 rtl:space-x-reverse">
                        <img src="/public/logoTrack.drawio.png" class="h-8" alt="Logo" />
                        <span
                            class="self-center text-2xl font-semibold whitespace-nowrap text-yellow-500">JikoTrack</span>
                    </nuxt-link>
                    <div class="flex items-center md:order-2 space-x-3 md:space-x-0 rtl:space-x-reverse relative">
                        <companyDdown />
                    </div>
                    <div class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1"
                        id="navbar-user">
                        <ul
                            class="flex flex-col font-medium p-4 md:p-0 mt-4 border border-gray-100 rounded-lg bg-gray-50 md:space-x-8 rtl:space-x-reverse md:flex-row md:mt-0 md:border-0 md:bg-white dark:bg-gray-800 dark:border-gray-700">
                            <li>
                                <NuxtLink to=""
                                    class="block py-2 px-3 text-black bg-yellow-500 rounded md:bg-transparent md:text-yellow-500 md:p-0 md:dark:text-yellow-400"
                                    aria-current="page">Home</NuxtLink>
                            </li>
                            <li>
                                <NuxtLink to=""
                                    class="block py-2 px-3 text-black rounded hover:bg-yellow-500 md:hover:bg-transparent md:hover:text-yellow-500 md:p-0 dark:text-gray-300 md:dark:hover:text-yellow-400 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">
                                    About</NuxtLink>
                            </li>
                            <li>
                                <NuxtLink to=""
                                    class="block py-2 px-3 text-gray-900 rounded hover:bg-yellow-500 md:hover:bg-transparent md:hover:text-yellow-500 md:p-0 dark:text-gray-300 md:dark:hover:text-yellow-400 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">
                                    Services</NuxtLink>
                            </li>
                            <li>
                                <NuxtLink to=""
                                    class="block py-2 px-3 text-gray-900 rounded hover:bg-yellow-500 md:hover:bg-transparent md:hover:text-yellow-500 md:p-0 dark:text-gray-300 md:dark:hover:text-yellow-400 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">
                                    Pricing</NuxtLink>
                            </li>
                            <li>
                                <NuxtLink to=""
                                    class="block py-2 px-3 text-gray-900 rounded hover:bg-yellow-500 md:hover:bg-transparent md:hover:text-yellow-500 md:p-0 dark:text-gray-300 md:dark:hover:text-yellow-400 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700">
                                    Contact</NuxtLink>
                            </li>
                        </ul>
                    </div>
                </div>

            </nav>
        </header>
    </div>
    <div class="min-h-screen flex-1">
        <slot />
    </div>
    <div>
        <footer class="bg-gray-50 dark:bg-gray-800">
            <div class="mx-auto max-w-screen-xl px-4 py-8 sm:px-6 lg:px-8">
                <div class="sm:flex sm:items-center sm:justify-between">
                    <p class="mt-4 text-center text-sm text-gray-500 dark:text-gray-300 lg:mt-0 lg:text-center">
                        Copyright &copy; 2024. All rights reserved.
                    </p>
                </div>
            </div>
        </footer>
    </div>
</template>

<script>
import companyDdown from './companyDdown.vue'

export default {
    components: {
        companyDdown,
    },
    data() {
        return {
            isOpen: false
        }
    }
}
</script>

<style>
.router-link-exact-active {
    color: rgb(251, 191, 36);
}
</style>
