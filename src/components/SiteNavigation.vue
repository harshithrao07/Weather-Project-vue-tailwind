<template>
    <header class="sticky top-0 bg-weather-primary shadow-lg">
        <nav class="container flex flex-col 
        sm:flex-row items-center gap-4 text-white py-6">
        <RouterLink :to="{name: 'home'}">
            <div class="flex items-center gap-3 flex-1">
                <i class="fa-solid fa-sun text-2xl"></i>
                <p class="text-2xl">The Local Weather</p>
            </div>
         </RouterLink>

         <div class="flex gap-3 flex-1 justify-end">
            <i class="fa-solid fa-circle-info text-xl 
            hover:text-weather-secondary duration-150 cursor-pointer" @click="handleClick"></i>
         </div>

         <BaseModal v-if="modalActive" :modalActive="modalActive" @close="handleClick">
            <div class="text-black">
              <h1 class="text-2xl mb-1">About:</h1>
              <p class="mb-4">
                The Local Weather allows you to track the current and
                future weather of cities of your choosing.
              </p>
              <h2 class="text-2xl">How it works:</h2>
              <ul class= "list-inside mb-4 list-disc">
                <li>
                  Search for your city by entering the name into the
                  search bar.
                </li>
                <li>
                  Select a city within the results, this will take
                  you to the current weather for your selection.
                </li>
              </ul>

              <h2 class="text-2xl mt-4">Created by Harshith Rao with ❤️</h2>
            </div>
        </BaseModal>
        </nav>
    </header>
</template>

<script setup>
import { RouterLink } from "vue-router" 
import BaseModal from "./BaseModal.vue"
import { ref } from "vue"


const modalActive = ref(false)

const handleClick = () => {
    modalActive.value = !modalActive.value
}

</script>

<style>
header{
background: rgba( 100, 197, 237, 0.25 );
box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
backdrop-filter: blur( 4px );
-webkit-backdrop-filter: blur( 4px );
border-radius: 10px;
border: 1px solid rgba( 255, 255, 255, 0.18 );
}
</style>
