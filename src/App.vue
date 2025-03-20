<template>
  <div class="app-container">
    <TopNav />
    <main class="content">
      <HomePage />
    </main>
  </div>
</template>

<script setup>
import TopNav from "@/components/Navigation/TopNav.vue";
import HomePage from "@/views/HomePage.vue";
</script>

<style>
/* Global Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  margin: 0;
  background-color: #25293c;
  color: #fff;
  font-family: "Inter", sans-serif;
}

.app-container {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

.content {
  flex: 1;
  padding: 2rem;
  overflow-y: auto;
}
</style>
