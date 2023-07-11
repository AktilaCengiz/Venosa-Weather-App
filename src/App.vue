<script setup>
import { provide, ref } from "vue";

import Navbar from "./components/Navbar.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";
var liItems = [
  { name: "Venosa Studio", link: "https://venosastudio.com" },
];
provide("theme", ref(localStorage.getItem("darkTheme") === "true" ? true : false));
provide("loaded", ref(false));

if(localStorage.getItem("darkTheme") === "true") {
    document.documentElement.classList.add("dark");
} else {
    document.documentElement.classList.remove("dark");
}

</script>

<template>
  <Navbar sitename="Venosa Weather" :liItems="liItems" />
  <Main />
  <Footer />

</template>