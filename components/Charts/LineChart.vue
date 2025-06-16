<script lang="ts" setup>
const chartData = [
  {
    date: 'Jan 23',
    users: 2890,
    sales: 2338,
  },
  {
    date: 'Feb 23',
    users: 2756,
    sales: 2103,
  },
  {
    date: 'Mar 23',
    users: 3322,
    sales: 2194,
  },
  {
    date: 'Apr 23',
    users: 3470,
    sales: 2108,
  },
  {
    date: 'May 23',
    users: 3475,
    sales: 1812,
  },
  {
    date: 'Jun 23',
    users: 3129,
    sales: 1726,
  },
  {
    date: 'Jul 23',
    users: 3490,
    sales: 1982,
  },
  {
    date: 'Aug 23',
    users: 2903,
    sales: 2012,
  },
  {
    date: 'Sep 23',
    users: 2643,
    sales: 2342,
  },
  {
    date: 'Oct 23',
    users: 2837,
    sales: 2473,
  },
  {
    date: 'Nov 23',
    users: 2954,
    sales: 3848,
  },
  {
    date: 'Dec 23',
    users: 3239,
    sales: 3736,
  },
]

const categories = {
  users: { name: 'Total users', color: '#3b82f6' },
  sales: { name: 'Total sales', color: '#22c55e' },
}

const xFormatter = (i: number): string | number => `${chartData[i]?.date}`
</script>
<template>
  <LineChart
    :data="chartData"
    :height="150"
    y-label="Sales"
    :x-num-ticks="4"
    :y-num-ticks="4"
    :categories="categories"
    :x-formatter="xFormatter"
    :y-grid-line="true"
    :curve-type="CurveType.Linear"
    :legend-position="LegendPosition.Top"
    :hide-legend="false"
  />
</template>
