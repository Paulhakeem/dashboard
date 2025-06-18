<script setup>
import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'

const list = ref([
  {
    title: 'Budgeting',
    value: '$12,345',
    icon: 'healthicons:low-income-level-24px',
  },
  {
    title: 'Income',
    value: '$1,234',
    icon: "streamline:graph-bar-increase-solid",
  },
  {
    title: 'Expenses',
    value: '$12,345',
    icon: 'streamline:graph-bar-decrease-solid',
  },
  {
    title: 'Investments',
    value: '$1,234',
    icon: 'solar:graph-up-bold',
  },
  { title: 'Debts',
    value: '$12,345',
    icon: 'streamline-block:other-ui-graph',
  },
  {title: 'Financial Goals',
    value: '$921,234',
    icon: 'streamline:graph-arrow-increase-remix',
  }
])
</script>

<template>
  <Card class="shadow-lg">
    <CardHeader>
      <CardTitle class="bg-[#3b82f6] flex justify-between items-center py-3 px-2 rounded-t-lg">
        <span class="text-gray-200 text-sm font-semibold ">Total Value</span>
        <span class=" text-sm font-semibold text-gray-200">Balance</span>

      </CardTitle>
      <CardDescription>
        <ul v-for="(card, index) in list" :key="index" class="flex items-center justify-between py-3 border-b border-gray-200">
          <li class="text-sm font-semibold text-[#242632] flex items-center gap-2">
            <Icon size="25" :name="card.icon" class="text-[#3b82f6]" />
            {{card.title}}</li>
          <li class="text-sm font-semibold text-[#242632]">{{card.value}}</li>
        </ul>
      </CardDescription>
    </CardHeader>
  </Card>
</template>