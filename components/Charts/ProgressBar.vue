<script lang="ts" setup>
type chartDataItem = {
  month: string;
  budget: number;
};

const chartData = [
  { month: "January", budget: 186 },
  { month: "February", budget: 305 },
  { month: "March", budget: 237 },
  { month: "April", budget: 260 },
  { month: "May", budget: 209 },
  { month: "June", budget: 250 },
];

const categories: Record<string, BulletLegendItemInterface> = {
  budget: { name: "Budget", color: "#3b82f6" },
};

const xFormatter = (i: number): string | number => `${chartData[i]?.month}`;
</script>
<template>
  <LineChart
    :data="chartData"
    :height="200"
    y-label="Value"
    :x-num-ticks="2"
    :categories="categories"
    :x-formatter="xFormatter"
    :y-grid-line="true"
    :curve-type="CurveType.MonotoneX"
    :legend-position="LegendPosition.Top"
    :hide-legend="false"
  />
</template>
