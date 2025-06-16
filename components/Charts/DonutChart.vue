<script setup>
const donutData = ref([35, 25, 20, 15, 5]); // Percentages

const marketShareLabels = [
  { name: "Goal A", color: "#3b82f6" }, // Blue
  { name: "Goal B", color: "#22c55e" }, // Green
  { name: "Goal C", color: "#f59e0b" }, // Amber
  { name: "Goal D", color: "#a855f7" }, // Purple
  { name: "Other", color: "#06b6d4" }, // Cyan
];
</script>

<template>
  <DonutChart
    :data="donutData"
    :height="300"
    :radius="0"
    :type="'full'"
    :labels="marketShareLabels"
  >
    <div class="absolute text-center">
      <div class="font-semibold text-gray-700">Income Goals</div>
      <h2 class="font-bold text-4xl text-gray-700">58%</h2>
    </div>
  </DonutChart>
</template>
