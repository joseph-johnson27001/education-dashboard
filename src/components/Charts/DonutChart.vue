<template>
  <div class="donut-chart">
    <div class="chart-center-text">
      <div>{{ hoveredLabel.name }}</div>
      <div class="value">{{ hoveredLabel.value }}</div>
    </div>
    <apexchart
      type="donut"
      :options="chartOptions"
      :series="chartSeries"
      @dataPointMouseEnter="updateHoverText"
      @dataPointMouseLeave="resetHoverText"
      :height="225"
    />
  </div>
</template>

<script>
import { defineComponent, ref, computed } from "vue";
import VueApexCharts from "vue3-apexcharts";

export default defineComponent({
  components: {
    apexchart: VueApexCharts,
  },
  setup() {
    const chartSeries = ref([25, 20, 15, 10, 18, 12]);
    const labels = [
      "HTML/CSS",
      "JavaScript",
      "React",
      "Node.js",
      "Python",
      "Git/GitHub",
    ];

    const totalHours = computed(() =>
      chartSeries.value.reduce((a, b) => a + b, 0)
    );

    const hoveredLabel = ref({
      name: `Total Learning Time`,
      value: `${totalHours.value} hrs`,
    });

    const chartOptions = ref({
      chart: {
        toolbar: { show: false },
      },
      labels: labels,
      colors: [
        "#7367f0",
        "#00bad1",
        "#28c76f",
        "#ff4c51",
        "#ff9f43",
        "#7a4c8e",
      ],
      dataLabels: { enabled: false },
      tooltip: {
        enabled: false,
        // theme: "dark",
        // y: {
        //   formatter: (val) => `${val} hrs`,
        // },
      },
      legend: { show: false },
      plotOptions: {
        pie: {
          donut: {
            size: "75%",
            labels: { show: false },
          },
        },
      },
      stroke: { show: false },
    });

    const updateHoverText = (event, chartContext, { dataPointIndex }) => {
      hoveredLabel.value = {
        name: labels[dataPointIndex],
        value: `${chartSeries.value[dataPointIndex]} hrs`,
      };
    };

    const resetHoverText = () => {
      hoveredLabel.value = {
        name: "Total Learning Time",
        value: `${totalHours.value} hrs`,
      };
    };

    return {
      chartSeries,
      chartOptions,
      hoveredLabel,
      updateHoverText,
      resetHoverText,
    };
  },
});
</script>

<style scoped>
.donut-chart {
  position: relative;
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.chart-center-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 0.9rem;
  font-family: "Inter";
  color: #fff;
  font-weight: 600;
  text-align: center;
}

.chart-center-text .value {
  font-size: 1.1rem;
  font-weight: 500;
  color: #c1bfd6;
}

@media (max-width: 300px) {
  .donut-chart {
    display: none;
  }
}
</style>
