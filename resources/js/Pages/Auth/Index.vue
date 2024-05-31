<template>
    <Head>
        <title>Accreditation</title>
    </Head>

    <div class="flex justify-around w-full h-screen">
        <div class="self-center hidden w-72 h-fit lg:block">
            <img src="/img/nuc-logo.png" alt="" class="w-full">   

            <div class="w-full my-5 text-2xl font-bold text-center text-dnscGreen">NUC ACCREDITATION</div>
        </div>
        <div class="">
            <LoginComponent v-if="$page.url.startsWith('/index')" />
            <ForgotComponent v-if="$page.url.startsWith('/forgot')" />
            <RegisterComponent v-if="$page.url.startsWith('/register')" />
        </div>

    </div>

</template>

<script setup>
import LoginComponent from '../../Components/Auth/Login.vue'
import ForgotComponent from '../../Components/Auth/Forgot.vue'
import RegisterComponent from '../../Components/Auth/Register.vue'
import { Head } from '@inertiajs/inertia-vue3'
import { onBeforeMount, onMounted } from '@vue/runtime-core'
import { Inertia } from '@inertiajs/inertia'
import axios from 'axios';

const instance = axios.create({
    baseURL: 'http://127.0.0.1:8000/',
});

instance.interceptors.response.use(
    response => {
        //console.log(response)
    },
    error => {
        if (error.response.status === 401) {
            // Redirect to login page or show an error message
            location.reload();
        }
        //console.log('adfasdf')
        return Promise.reject(error);
    }
);

const props = defineProps({
    user: Object,
})

onBeforeMount(() => {
    if(props.user)
    {
        Inertia.get('/verify_user')
    }
})


</script>