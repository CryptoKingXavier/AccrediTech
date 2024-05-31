<template>
    <div class="flex flex-col items-center justify-center w-full h-screen">
        <div class="w-full my-5 text-2xl font-bold text-center text-dnscGreen">NUC ACCREDITATION</div>
        <Loading />
    </div>
</template>
<script setup>
import Loading from '../Components/Loading.vue'
import { Inertia } from "@inertiajs/inertia";


const props = defineProps({
    authU: String,
    authA: String,
    token: String
})

Inertia.post('/redirected_login', {
    username: props.authU,
    password: props.authA,
})
</script>