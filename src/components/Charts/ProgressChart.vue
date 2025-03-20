<template>
  <div class="progress-chart">
    <apexchart
      type="bar"
      :options="chartOptions"
      :series="chartSeries"
      height="350"
    />
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import VueApexCharts from "vue3-apexcharts";

export default defineComponent({
  components: {
    apexchart: VueApexCharts,
  },
  setup() {
    const chartOptions = ref({
      chart: {
        type: "bar",
        height: "350",
        toolbar: {
          show: false,
        },
      },

      grid: {
        show: true,
        borderColor: "#686a80",
        strokeDashArray: 5,
        xaxis: {
          lines: {
            show: true,
          },
        },
        yaxis: {
          lines: {
            show: false,
          },
        },
      },
      xaxis: {
        categories: [
          "Math",
          "Science",
          "History",
          "Geography",
          "Literature",
          "Art",
        ],
        labels: {
          style: {
            colors: "#c1bfd6",
          },
        },
      },
      yaxis: {
        labels: {
          style: {
            colors: "#c1bfd6",
          },
        },
      },
      plotOptions: {
        bar: {
          horizontal: true, // Make the bar chart horizontal
        },
      },
      fill: {
        colors: [
          "#00c1d4",
          "#4d89e2",
          "#f96c50",
          "#f1b233",
          "#5ab76d",
          "#b278e6",
        ],
        opacity: 0.9,
      },
      dataLabels: {
        enabled: true,
        textAnchor: "middle",
        style: {
          fontSize: "14px",
          fontWeight: "bold",
          colors: ["#fff"],
        },
        formatter: function (val, opts) {
          // Returning the name of the area instead of the value
          return opts.w.globals.labels[opts.seriesIndex];
        },
      },
      tooltip: {
        theme: "dark",
        x: {
          show: true,
        },
        y: {
          formatter: (value) => `${value}%`,
        },
      },
    });

    const chartSeries = ref([
      {
        name: "Progress",
        data: [75, 80, 65, 55, 90, 60], // Progress data for each category
      },
    ]);

    return {
      chartOptions,
      chartSeries,
    };
  },
});
</script>

<style scoped>
.progress-chart {
  margin-top: 2rem;
}
</style>
