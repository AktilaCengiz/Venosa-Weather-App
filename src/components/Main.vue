<!-- eslint-disable vue/multi-word-component-names -->
<script setup>

import { inject } from "vue";

var loadedInfo = inject("loaded");

setTimeout(() => {
    loadedInfo.value = true;
}, 300);

</script>

<template>
    <div class="w-screen bg-gray-200 dark:bg-[#090909] w-screen">
        <div class="flex flex-col justify-center ml-0  items-center md:h-[420px] ">
            <h1 class="text-4xl dark:text-white text-black md:mt-0 font-Raleway mt-20">Hava Durumu</h1>
            <hr class="dark:text-white text-black mx-5 mb-5" />

            <form class="mb-5">
                <input type="text" class="border-2 border-gray-300 bg-white h-10 px-5 pr-16 rounded-lg text-sm focus:outline-none" placeholder="Şehir Giriniz" />

                <button class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded inline-flex items-center ml-2">
                    <i class="bi bi-search"></i>
                </button>

            </form>

            <div v-if="loadedInfo == false" class="border border-blue-300 shadow rounded-md p-4 max-w-sm w-full mx-auto">
                 <div div class="animate-pulse flex space-x-4">
                 <div class="rounded-full bg-slate-700 h-10 w-10"></div>
                <div class="flex-1 space-y-6 py-1">
                <div class="h-2 bg-slate-700 rounded"></div>
                <div class="space-y-3">
                 <div class="grid grid-cols-3 gap-4">
                     <div class="h-2 bg-slate-700 rounded col-span-2"></div>
                     <div class="h-2 bg-slate-700 rounded col-span-1"></div>
                    </div>
                 <div class="h-2 bg-slate-700 rounded"></div>
                 </div>
             </div>
             </div>
            </div>
            <div class="rounded-xl flex p-10" id="ww_14ea9190e6f0b" v='1.3' loc='id' a='{"t":"horizontal","lang":"tr","sl_lpl":1,"ids":[],"font":"Arial","sl_ics":"one_a","sl_sot":"celsius","cl_bkg":"image","cl_font":"#FFFFFF","cl_cloud":"#FFFFFF","cl_persp":"#81D4FA","cl_sun":"#FFC107","cl_moon":"#FFC107","cl_thund":"#FF5722"}'>Weather Data Source: <a href="https://oneweather.org/fr/paris/25_days/" id="ww_14ea9190e6f0b_u" target="_blank">Paris meteo a 25 jours</a></div>

        </div>

    </div>
</template>

