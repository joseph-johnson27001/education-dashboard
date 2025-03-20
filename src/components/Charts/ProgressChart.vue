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
import { defineComponent, ref, onMounted } from "vue";
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
        animations: {
          enabled: true,
          easing: "linear",
          dynamicAnimation: {
            enabled: true,
            speed: 750,
          },
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
          show: true,
          style: {
            colors: "#c1bfd6",
            fontSize: "12px",
            fontFamily: "Assistant",
          },
        },
      },
      yaxis: {
        max: 100,
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
        data: [],
      },
    ]);

    const allData = [
      { x: "Math", y: 85, fillColor: "#7367f0" },
      { x: "Science", y: 80, fillColor: "#00bad1" },
      { x: "History", y: 80, fillColor: "#28c76f" },
      { x: "Geography", y: 70, fillColor: "#ff4c51" },
      { x: "Literature", y: 60, fillColor: "#ff9f43" },
      { x: "Art", y: 50, fillColor: "#7a4c8e" },
    ];

    onMounted(() => {
      setTimeout(() => {
        chartSeries.value[0].data = allData;
      }, 100);
    });

    return {
      chartOptions,
      chartSeries,
    };
  },
});
</script>
