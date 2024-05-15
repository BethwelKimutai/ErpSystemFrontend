<template>
    <div class="h-screen bg-slate-50 flex justify-center items-center w-full">
        <form @submit.prevent="submit">
            <div class="bg-white px-10 py-8 rounded-xl w-screen shadow-md max-w-sm">
                <img class="h-16 mb-6 mx-auto" src="/public/logoTrack.drawio.png" alt="">
                <div class="space-y-4">
                    <h1 class="text-center text-2xl font-semibold text-gray-600">Sign Up</h1>
                    <div>
                        <label for="name" class="block mb-1 text-gray-600 font-semibold">Name</label>
                        <input v-model="name" type="text" class="bg-indigo-50 px-4 py-2 outline-none rounded-md w-full" />
                    </div>
                    <div>
                        <label for="email" class="block mb-1 text-gray-600 font-semibold">Email</label>
                        <input v-model="email" type="text" class="bg-indigo-50 px-4 py-2 outline-none rounded-md w-full" />
                    </div>
                    <div>
                        <label for="password" class="block mb-1 text-gray-600 font-semibold">Password</label>
                        <input v-model="password" type="password" class="bg-indigo-50 px-4 py-2 outline-none rounded-md w-full" />
                    </div>
                </div>
                <button class="mt-4 w-full bg-yellow-500 font-semibold py-2 rounded-md  tracking-wide">Signup</button>
                <div>
                    <p class="mt-5 text-sm font-light text-yellow-500 dark:text-black">
                        Already have an account? <nuxt-link to="/Signup/login"
                            class="font-medium text-primary-600 hover:underline dark:text-yellow-500">Login
                            </nuxt-link>
                    </p>
                </div>
            </div>

        </form>
    </div>
</template>

<script>
export default{
    name : "SignUp",
    data(){
        return{
            name: '',
            email: '',
            password: ''
        }
    },
    methods:{
        async submit(){
            await fetch(' http://127.0.0.1:8000/jikoTrack/register',{
                method: 'POST',
                headers:{'Content-Type':'application/json'},
                body: JSON.stringify({
                    name: this.name,
                    email: this.email,
                    password: this.password
                })
            });

            await this.$router.push('/Signup/login')
        }
    }
}
</script>

<style>
</style>