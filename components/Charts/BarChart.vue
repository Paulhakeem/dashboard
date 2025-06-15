<script setup>
const RevenueData = [
  { month: 'January', profit: 186, loss: 80 },
  { month: 'February', profit: 305, loss: 200 },
  { month: 'March', profit: 237, loss: 120 },
  { month: 'April', profit: 73, loss: 190 },
  { month: 'May', profit: 209, loss: 130 },
  { month: 'June', profit: 214, loss: 140 },
]
const RevenueCategoriesMultple = {
  profit: { name: 'Profit', color: '#3b82f6' },
  loss: { name: 'Loss', color: '#f44336' },
}

const yFormatter = (i) => `${RevenueData[i]?.month}`
</script>
<template>
  <BarChart
    :data="RevenueData"
    :stacked="true"
    :height="300"
    :categories="RevenueCategoriesMultple"
    :y-axis="['profit', 'loss']"
    :group-padding="0"
    :bar-padding="0.2"
    :xNumTicks="6"
    :radius="4"
    :orientation="Orientation.Horizontal"
    :x-formatter="(i) => i"
    :y-formatter="(i) => `${RevenueData[i]?.month}`"
    :legend-position="LegendPosition.Top"
    :hide-legend="false"
    :x-grid-line="true"
  />
</template>
