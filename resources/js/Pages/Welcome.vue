<template>

    <div class="flex justify-around items-center bg-gray-100 min-h-screen">
        <div>
            <!-- Будет лого -->
        </div>
        <div class="text-center">
            <h1 class="text-4xl font-semibold">
                Social Networke  
            </h1>

            <div v-if="canLogin" class="flex justify-center space-x-6 mt-5">
                <inertia-link href="#" v-if="$page.props.user" class="text-lg text-gray-700 underline">
                    Dashboard
                </inertia-link>
                <template v-else>
                    <inertia-link :href="route('login')" class="text-white bg-gray-800 rounded px-3 py-1 hover:bg-gray-500">Login</inertia-link>
                    <inertia-link :href="route('register')" v-if="canRegister" class="text-white bg-gray-800 rounded px-3 py-1 hover:bg-gray-500">
                        Register
                    </inertia-link>
                </template>
            </div>
            <p class="mt-10">{{ users }} active members</p>
            
        </div>
    </div>
</template>

<script lang="js">
    export default {
        props: {
            users: Number,
            canLogin: Boolean,
            canRegister: Boolean,
            laravelVersion: String,
            phpVersion: String,
        }
    }
</script>
