<template>
  <div>
    <line-chartjs :chart-data="chartData" :chart-options="chartOptions" />
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  setup() {
    const chartData = {
      labels: ["January", "February", "March", "April", "May", "June", "July"],
      datasets: [
        {
          label: "Birt Rate",
          backgroundColor: "#f87979",
          data: [40, 39, 10, 40, 39, 80, 40],
        },
      ],
    };

    const chartOptions = {
      responsive: true,
      maintainAspectRatio: false,
    };
    return { chartData, chartOptions };
  },
};
</script>
