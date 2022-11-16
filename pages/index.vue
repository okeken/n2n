<template>
  <div>
    <button @click="increment">increase</button>
    {{ counter }}
    <line-chartjs :chart-data="chartData" :chart-options="chartOptions" />
  </div>
</template>

<script>
import { ref } from "@nuxtjs/composition-api";
export default {
  name: "IndexPage",
  setup() {
    const counter = ref(0);
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

    const increment = () => {
      counter.value = counter.value + 1;
    };
    return { chartData, chartOptions, counter, increment };
  },
};
</script>
