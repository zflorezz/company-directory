<template>
<div class="flex justify-center gap-4 p-5">

    <button @click="prevPage" :disabled="activePage === 1" class="rounded-md bg-purple-300 p-2 font-medium text-slate-700 shadow-md-">PREV</button>
   
    <button v-for="page in pages" :key="page" class="rounded-md bg-pink-100 p-2 font-medium text-slate-700 shadow-md-" :class="page === activePage ? 'bg-pink-300 text-slate-700': ''"> {{ page }}</button>
   
    <button @click="nextPage" :disabled="activePage === pages" class="rounded-md bg-purple-300 p-2 font-medium text-slate-700 shadow-md">NEXT</button>

</div>

</template>

<script setup>
import { ref } from 'vue'
const pages = ref(10)
const activePage = ref(2)

const prevPage = () => {
    if (activePage.value > 1) {
        activePage.value--
    }

    console.log(activePage.value)
}

const nextPage = () => {
    if (activePage.value < pages.value) {
        activePage.value++
    }

    console.log(activePage.value)
}



</script>


