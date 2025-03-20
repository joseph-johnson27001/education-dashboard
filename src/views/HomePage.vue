<template>
  <div class="home-page">
    <div class="heading-area">
      <div>
        <div class="welcome-heading">Welcome back, Joanne!</div>
        <div class="welcome-back-message">
          Keep pushing forward, your next milestone is just around the corner.
          Let's get studying!
        </div>
        <div class="kpi-area">
          <KpiCard
            v-for="(kpi, index) in kpiData"
            :key="index"
            :icon="kpi.icon"
            :label="kpi.label"
            :value="kpi.value"
            :iconColor="kpi.iconColor"
          />
        </div>
      </div>

      <div class="donut-chart-section">
        <DonutChart />
      </div>
    </div>

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
import DonutChart from "@/components/Charts/DonutChart.vue";

export default {
  components: {
    KpiCard,
    ProgressChart,
    DonutChart,
  },
  data() {
    return {
      kpiData: [
        {
          icon: "far fa-user",
          label: "Courses Completed",
          value: "12",
          iconColor: "#3498db",
        },
        {
          icon: "far fa-clock",
          label: "Time Studied",
          value: "120 hrs",
          iconColor: "#00bcd4",
        },
        {
          icon: "far fa-chart-bar",
          label: "Average Course Score",
          value: "85%",
          iconColor: "#ff9f43",
        },
        {
          icon: "far fa-calendar-check",
          label: "Upcoming Deadline",
          value: "March 25, 2025",
          iconColor: "#28c76f",
        },
        {
          icon: "far fa-star",
          label: "Total Achievements",
          value: "5",
          iconColor: "#9b59b6",
        },
        {
          icon: "far fa-lightbulb",
          label: "Completed Challenges",
          value: "8",
          iconColor: "#ffde21",
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
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.heading-area {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 20px;
}

.donut-chart-section {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 8px;
}

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

.welcome-heading {
  padding-top: 10px;
  font-size: 20px;
  color: #fff;
  margin-bottom: 10px;
}

.welcome-back-message {
  font-size: 14px;
  color: #c1bfd6;
  margin-bottom: 20px;
  font-weight: 600;
}
</style>
