<template>
  <div class="app-container">
    <TopNav />
    <main class="content">
      <HomePage />
    </main>
    <DashboardButton />
  </div>
</template>

<script setup>
import TopNav from "@/components/Navigation/TopNav.vue";
import HomePage from "@/views/HomePage.vue";
import DashboardButton from "./components/UI/DashboardButton.vue";
</script>

<style>
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
  align-items: center;
}

.content {
  flex: 1;
  padding: 10px 20px 20px 20px;
  max-width: 1400px;
  box-sizing: border-box;
  width: 100%;
  margin: 0 auto;
}
</style>
