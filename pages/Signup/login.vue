<template>
    <div class="h-screen bg-slate-50 flex justify-center items-center w-full">
        <form @submit.prevent="submit">
            <div class="bg-white px-10 py-8 rounded-xl w-screen shadow-md max-w-sm">
                <img class="h-14 mb-4 mx-auto" src="/public/logoTrack.drawio.png" alt="">
                <div class="space-y-4">
                    <h1 class="text-center text-2xl font-semibold text-gray-600">Login</h1>
                    <div>
                        <label for="email" class="block mb-1 text-gray-600 font-semibold">Email</label>
                        <input id="email" v-model="email" type="text"
                            class="bg-indigo-50 px-4 py-2 outline-none rounded-md w-full" />
                    </div>
                    <div>
                        <label for="password" class="block mb-1 text-gray-600 font-semibold">Password</label>
                        <input id="password" v-model="password" type="password"
                            class="bg-indigo-50 px-4 py-2 outline-none rounded-md w-full" />
                    </div>
                    <div class="flex items-center justify-between">
                        <div class="flex items-start">
                            <div class="flex items-center h-5">
                                <input id="remember" aria-describedby="remember" type="checkbox"
                                    class="w-4 h-4 border border-gray-300 rounded bg-yellow-500 focus:ring-3 focus:ring-yellow-500 dark:bg-gray-700 dark:border-gray-600 dark:focus:ring-yellow-500 dark:ring-offset-gray-800"
                                    required="">
                            </div>
                            <div class="ml-3 text-sm">
                                <label for="remember" class="text-gray-500 dark:text-black">Remember
                                    me</label>
                            </div>
                        </div>
                        <nuxt-link to=""
                            class="text-sm font-medium text-primary-600 hover:underline dark:text-yellow-500">Forgot
                            password?</nuxt-link>
                    </div>
                </div>
                <button type="submit"
                    class="mt-4 w-full bg-yellow-500 font-semibold py-2 rounded-md  tracking-wide">Login</button>
                <div>
                    <p class="mt-5 text-sm font-light text-yellow-500 dark:text-black">
                        Don’t have an account yet? <nuxt-link to="/Signup/signup"
                            class="font-medium text-primary-600 hover:underline dark:text-yellow-500">Sign
                            up</nuxt-link>
                    </p>
                </div>
            </div>

        </form>
    </div>
</template>

<script>
export default {
    name: "login",
    data() {
        return {
            email: '',
            password: '',
            alertMessage: '',
            showAlert: false,
        }
    },

    methods: {
        async submit() {
            try {
                const response = await fetch(' http://127.0.0.1:8000/jikoTrack/login', {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    credentials: 'include',
                    body: JSON.stringify({
                        email: this.email,
                        password: this.password
                    })
                });

                if (response.ok) {
                    this.alertMessage = 'successAlert /',
                        this.showAlert = true,

                        setTimeout(() => {
                            this.$router.push('/accounting');
                        }, 2000)
                }
                else {
                    this.alertMessage = 'errorAlert /',
                        this.showAlert = true;
                }
            }
            catch (error) {
                console.error('Error:', error);
                this.alertMessage = 'An error has occured while trying to log in.Please Try again later';
                this.showAlert = true;
            }

        }
    }
}
</script>

<style></style>