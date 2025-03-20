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
        toolbar: {
          show: false,
        },
      },
      grid: {
        show: true,
        borderColor: "#686a80",
        strokeDashArray: 10,
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
          "Maths",
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
          show: false,
        },
      },
      plotOptions: {
        bar: {
          horizontal: true,
          borderRadius: 8,
          borderRadiusApplication: "end",
        },
      },
      dataLabels: {
        enabled: true,
        textAnchor: "middle",
        style: {
          fontSize: "14px",
          fontFamily: "Assistant",
          colors: ["#fff"],
        },
        formatter: function (val, opts) {
          return opts.w.globals.labels[opts.dataPointIndex];
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
        data: [
          { x: "Math", y: 75, fillColor: "#7367f0" },
          { x: "Science", y: 80, fillColor: "#00bad1" },
          { x: "History", y: 65, fillColor: "#28c76f" },
          { x: "Geography", y: 55, fillColor: "#ff4c51" },
          { x: "Literature", y: 90, fillColor: "#ff9f43" },
          { x: "Art", y: 60, fillColor: "#7a4c8e" },
        ],
      },
    ]);

    return {
      chartOptions,
      chartSeries,
    };
  },
});
</script>
