<template>
    <nav class="bg-red-700">
        <div class="container flex items-center justify-between mx-auto">
            <div class="flex items-center space-x-4">
                <noto:video-camera class="w-16 h-16" />
                <p class="text-4xl tracking-wider text-transparent bg-black font-extralight bg-clip-text" >Movies<span class="font-bold" >DB</span></p>
            </div>
            <div>
                <div v-if="isAuthenticated" class="flex items-center space-x-4" >
                    <p class="text-white" >Welcome {{ user?.displayName }}</p>
                    <button @click="signOut" class="px-8 py-2 font-semibold bg-red-500 rounded-full focus:ring-red-900 focus:ring-4 focus:outline-none text-black hover:bg-red-900" >
                        Logout
                    </button>
                </div>
                <div v-else >
                    <button @click="signIn" class="px-8 py-2 font-semibold bg-green-500 rounded-full focus:ring-green-900 focus:ring-4 focus:outline-none text-black hover:bg-green-900" >
                        Login
                    </button>
                </div>
            </div>
        </div>
    </nav>
</template>

<script setup>
    import { authentication } from '~/helpers/useFirebase'

    const { signIn, signOut, isAuthenticated, user } = authentication()
</script>