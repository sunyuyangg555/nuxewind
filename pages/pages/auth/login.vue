<template>
    <div class="auth login">
        <div class="py-48 px-16">
            <h1 class="font-bold text-5xl">Welcome Back</h1>
            <p class='text-lg text-gray-600'>Please login to continue.</p>
            <form @submit.prevent="login" method="POST" class='mt-5'>
                <nx-input size='lg' label="Your Username"></nx-input>
                <nx-input size='lg' type="password" label="Your Password"></nx-input>
                <nx-button type="submit"  :block="true" :loading="loading" class='my-5 float-right' size="xl" shadow="lg">Login</nx-button>
                <div class="clear-right"></div>
                <nx-divider text="OR" />
                 <div class="mt-5 grid grid-cols-1 lg:grid-cols-2 gap-6">
                        <nx-button color="dark" shadow="lg" size='md' block="true">
                            <bootstrap-icon icon="github" size="md"></bootstrap-icon>
                            <span class='ml-4'>Login with Github</span>
                        </nx-button>
                        <nx-button color="danger" shadow="lg" size='md' block="true">
                            <bootstrap-icon icon="google" size="md"></bootstrap-icon>
                            <span class='ml-4'>Login with Google</span>
                        </nx-button>                
                </div>
            </form>
        </div>
    </div>
</template>
<script>
export default {
    layout: 'auth',
    data: () => ({
        loading: false,
    }),
    methods: {
        login() {
            this.loading = true;
            setTimeout(() => this.$router.push('/'),2000) 
        }
    }
}
</script>