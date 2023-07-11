<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
import { defineProps, inject } from "vue";

const props = defineProps({
  sitename: {
    type: String,
    required: true,
  },
  liItems: {
    type: Array,
    required: true,
  },
});

const theme = inject("theme");

const changeTheme = () => {
    if (theme.value == true) {
     theme.value = false;   
     document.documentElement.classList.remove("dark");
     localStorage.setItem("darkTheme", theme.value);
    } else {
        theme.value = true;
        document.documentElement.classList.add("dark");
        localStorage.setItem("darkTheme", theme.value);
    }
};

</script>

<template>
<nav class="bg-red-500 dark:bg-black/90 select-none">
  <div class="max-w-screen-xl flex flex-wrap items-center md:justify-around justify-end mx-auto p-4">
    <div>


    <div class="flex justify-center items-center gap-2 text-white">
        <span @click="changeTheme" v-if="theme == true"><i class="bi bi-brightness-low-fill md:text-3xl text-xl"></i></span>
        <span @click="changeTheme" v-else><i class="bi bi-moon-stars-fill md:text-3xl text-xl"></i></span>
    
 <a href="/" class="flex items-center">
      <span class="self-center md:text-2xl text-xl font-semibold font-Raleway whitespace-nowrap text-white flex items-center md:gap-3"> 
        {{ props.sitename }}</span>
      </a>
    </div>
  
</div>
    <a target="_blank" :href="liItems[0].link" class="text-white hover:text-red-200 px-4 py-2 text-sm font-medium">
    <button type="button" class="text-white bg-red-700 hover:bg-red-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-4 py-2 font-Raleway text-center mr-3 md:mr-0">{{liItems[0].name}}</button>
    </a>
 </div>
    

</nav>

</template>