<script lang="ts" setup>
type RevenueDataItem = {
  month: string
  mortgage: number
  consumer: number
}

const RevenueData: RevenueDataItem[] = [
  { month: 'January', mortgage: 186, consumer: 80 },
  { month: 'February', mortgage: 305, consumer: 200 },
  { month: 'March', mortgage: 237, consumer: 120 },
  { month: 'April', mortgage: 73, consumer: 190 },
  { month: 'May', mortgage: 209, consumer: 130 },
  { month: 'June', mortgage: 214, consumer: 140 },
]

const RevenueCategoriesMultple = {
  mortgage: { name: 'mortgage', color: '#3b82f6' },
  consumer: { name: 'consumer credit', color: '#22c55e' },
}

const xFormatter = (i: number): string => `${RevenueData[i]?.month}`
const yFormatter = (i: number) => i
</script>
<template>
  <BarChart
    :data="RevenueData"
    :height="100"
    :categories="RevenueCategoriesMultple"
    :y-axis="['mortgage', 'consumer']"
    :group-padding="0"
    :bar-padding="0.2"
    :xNumTicks="6"
    :radius="4"
    :x-formatter="xFormatter"
    :y-formatter="yFormatter"
    :legend-position="LegendPosition.Top"
    :hide-legend="false"
    :y-grid-line="true"
  />
</template>
