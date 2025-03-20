<template>
  <div class="home-page">
    <!-- KPIs Area (Placeholder) -->
    <div class="kpi-area">
      <p>Placeholder for KPIs</p>
    </div>

    <!-- Main Content Area (Graph + Sidebar) -->
    <div class="main-content">
      <!-- Progress Chart -->
      <div class="chart-area">
        <ProgressChart />
      </div>

      <!-- Sidebar (Empty for now, can be filled later) -->
      <div class="sidebar-area">
        <p>Placeholder for Sidebar Content</p>
      </div>
    </div>
  </div>
</template>

<script>
import ProgressChart from "@/components/Charts/ProgressChart.vue";

export default {
  components: {
    ProgressChart,
  },
};
</script>

<style scoped>
.home-page {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.kpi-area {
  text-align: center;
  background-color: #2e3348;
  padding: 1rem;
  color: #c1bfd6;
  border-radius: 8px;
}

.main-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 1.5rem;
}

.chart-area {
  background-color: #2e3348;
  border-radius: 8px;
}

.sidebar-area {
  background-color: #2e3348;
  padding: 2rem;
  border-radius: 8px;
  color: #c1bfd6;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
