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
          easing: "easeinout",
          dynamicAnimation: {
            enabled: true,
            speed: 600,
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
          "HTML/CSS",
          "JavaScript",
          "React",
          "Node.js",
          "Python",
          "Git/GitHub",
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
      { x: "HTML/CSS", y: 95, fillColor: "#7367f0" },
      { x: "JavaScript", y: 85, fillColor: "#00bad1" },
      { x: "React", y: 80, fillColor: "#28c76f" },
      { x: "Node.js", y: 70, fillColor: "#ff4c51" },
      { x: "Python", y: 60, fillColor: "#ff9f43" },
      { x: "Git/GitHub", y: 50, fillColor: "#7a4c8e" },
    ];

    onMounted(() => {
      setTimeout(() => {
        chartSeries.value[0].data = allData;
      }, 200);
    });

    return {
      chartOptions,
      chartSeries,
    };
  },
});
</script>

<style scoped>
.progress-chart {
  padding: 10px 10px 0px 10px;
  margin-left: -20px;
  margin-bottom: -20px;
  margin-top: -30px;
}
</style>
