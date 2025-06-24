<script setup>
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";
</script>

<template>
  <Card>
    <CardHeader>
        <CardTitle class="flex justify-between items-center py-3 px-2 rounded-t-lg">
        <span class="text-gray-600 text-sm font-semibold ">Budget</span>
        <span class=" text-xl font-bold text-[#00dc82]">$12,345</span>
      </CardTitle>
      <CardDescription>
        <ChartsProgressBar />
      </CardDescription>
    </CardHeader>
  </Card>
</template>
