<template>
  <div class="flex flex-col min-h-screen">
    <SideBar />
    <main class="flex-1">
      <router-view />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import SideBar from "@/components/appSideBar.vue";
import Footer from "@/components/appFooter.vue";
</script>

<style>
#main {
  margin: 0, ;
  padding: 0;
  height: 100%;
}
</style>