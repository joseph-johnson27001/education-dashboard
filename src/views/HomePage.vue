<template>
  <div class="home-page">
    <div class="heading-area">
      <div>
        <div class="welcome-heading">
          Welcome back, Joanne!
          <i class="far fa-solid fa-star"></i>
        </div>
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

      <div class="donut-chart-container">
        <div class="stats-section">
          <div class="weekly-stats">
            <div class="stats-heading">Weekly Change:</div>
            <div class="stats-time">{{ weeklyStats.time }}</div>
            <div class="stats-change">{{ weeklyStats.change }}</div>
          </div>

          <div class="monthly-stats">
            <div class="stats-heading">Monthly Change:</div>
            <div class="stats-time">{{ monthlyStats.time }}</div>
            <div class="stats-change">{{ monthlyStats.change }}</div>
          </div>
        </div>

        <div class="donut-chart-section">
          <DonutChart />
        </div>
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
          icon: "fa fa-medal",
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
      weeklyStats: {
        time: "18hrs 44mins",
        change: "+6.2%",
      },
      monthlyStats: {
        time: "82hrs 15mins",
        change: "+12.8%",
      },
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

.fa-star {
  color: gold;
  font-size: 1.4rem;
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

.donut-chart-container {
  display: flex;
  gap: 20px;
  align-items: flex-end;
}

.stats-section {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  gap: 10px;
  height: 100%;
}

.weekly-stats,
.monthly-stats {
  display: flex;
  flex-direction: column;
  border-radius: 8px;
}

.stats-heading {
  font-size: 1rem;
  font-family: "Inter";
  color: #fff;
  margin-bottom: 8px;
}

.stats-time {
  font-size: 16px;
  color: #c1bfd6;
  margin-bottom: 8px;
}

.stats-change {
  font-size: 14px;
  font-weight: 600;
  color: #28c76f;
  background-color: rgba(40, 199, 111, 0.2);
  padding: 5px 10px;
  border-radius: 6px;
  width: 70px;
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
