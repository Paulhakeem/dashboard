<script lang="ts" setup>
interface AreaChartItem {
  month: string
  investiments: number | string
}

const categories = {
    investiments: { name: 'Investiments', color: '#00dc82' },
}

const AreaChartData: AreaChartItem[] = [
  { month: 'January', investiments: 186 },
  { month: 'February', investiments: 305 },
  { month: 'March', investiments: 237 },
  { month: 'April', investiments: 73 },
  { month: 'May', investiments: 209 },
  { month: 'June', investiments: 214 },
]

const xFormatter = (i: number): string | number => `${AreaChartData[i]?.month}`
</script>
<template>
  <AreaChart
    :data="AreaChartData"
    :height="150"
    y-label="Value"
    x-label="Month"
    :categories="categories"
    :y-num-ticks="4"
    :x-num-ticks="7"
    :y-grid-line="true"
    :legend-position="LegendPosition.Top"
    :hide-legend="false"
    :x-formatter="xFormatter"
  />
</template>
