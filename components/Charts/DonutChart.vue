<script setup>
const donutData = ref([35, 25, 20, 15, 5]); // Percentages

const marketShareLabels = [
  { name: "Product A", color: "#3b82f6" }, // Blue
  { name: "Product B", color: "#22c55e" }, // Green
  { name: "Product C", color: "#f59e0b" }, // Amber
  { name: "Product D", color: "#a855f7" }, // Purple
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
      <div class="font-semibold">Income</div>
      <div class="text-(--ui-text-muted)">2 seconds ago</div>
    </div>
  </DonutChart>
</template>
