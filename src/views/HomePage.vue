<template>
  <div class="home-page">
    <div class="heading-area">
      <div class="kpi-area">
        <KpiCard
          v-for="(kpi, index) in kpiData"
          :key="index"
          :icon="kpi.icon"
          :label="kpi.label"
          :value="kpi.value"
        />
      </div>
    </div>

    <!-- Main Content Area (Graph + Sidebar) -->
    <div class="main-content">
      <div class="chart-area">
        <ProgressChart />
      </div>

      <div class="sidebar-area">
        <p>Placeholder for Sidebar Content</p>
      </div>
    </div>
  </div>
</template>

<script>
import KpiCard from "@/components/KPIs/KpiCard.vue";
import ProgressChart from "@/components/Charts/ProgressChart.vue";

export default {
  components: {
    KpiCard,
    ProgressChart,
  },
  data() {
    return {
      kpiData: [
        {
          icon: "fas fa-graduation-cap",
          label: "Courses Completed",
          value: "12",
        },
        { icon: "fas fa-clock", label: "Time Studied", value: "120 hrs" },
        {
          icon: "far fa-chart-bar",
          label: "Average Course Score",
          value: "85%",
        },
        {
          icon: "far fa-calendar",
          label: "Next Course Deadline",
          value: "March 25, 2025",
        },
      ],
    };
  },
};
</script>

<style scoped>
.home-page {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.kpi-area {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
}

.heading-area,
.main-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 20px;
}

.chart-area {
  background-color: #2e3348;
  border-radius: 8px;
  padding: 10px;
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
