<script setup>
import { Button } from "@/components/ui/button";
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";

const year = ref([
  {
    month: "January",
    value: "january",
    component: resolveComponent("BudgentJanuary"),
  },
  {
    month: "February",
    value: "february",
    component: resolveComponent("BudgentFebruary"),
  },
  {
    month: "March",
    value: "march",
    component: resolveComponent("BudgentMarch"),
  },
  {
    month: "April",
    value: "april",
    component: resolveComponent("BudgentApril"),
  },
  { month: "May", value: "may", component: resolveComponent("BudgentMay") },
  { month: "June", value: "june", component: resolveComponent("BudgentJune") },
  { month: "July", value: "july", component: resolveComponent("BudgentJuly") },
  {
    month: "August",
    value: "august",
    component: resolveComponent("BudgentAugust"),
  },
  {
    month: "September",
    value: "september",
    component: resolveComponent("BudgentSeptember"),
  },
  {
    month: "October",
    value: "october",
    component: resolveComponent("BudgentOctober"),
  },
  {
    month: "November",
    value: "november",
    component: resolveComponent("BudgentNovember"),
  },
  {
    month: "December",
    value: "december",
    component: resolveComponent("BudgentDecember"),
  },
]);
</script>

<template>
  <main>
    <Tabs class="w-full" default-value="january">
      <TabsList class="grid grid-cols-12 w-full">
        <TabsTrigger
          v-for="(month, index) in year"
          :key="index"
          :value="month.value"
          class="col-span-1 text-xs p-2 rounded hover:bg-blue-500 dark:hover:bg-gray-700"
        >
          {{ month.month }}
        </TabsTrigger>
      </TabsList>
      <!-- content -->
      <div v-for="(month, index) in year" :key="'content-' + index">
        <TabsContent :value="month.value" class="col-span-12 p-4">
          <Card class="w-full">
            <CardHeader>
              <CardTitle>{{ month.month }} Report</CardTitle>
              <CardDescription>
                This is where you can manage your budget for {{ month.month }}.
              </CardDescription>
            </CardHeader>
            <CardContent class="space-y-2">
              <component :is="month.component" />
            </CardContent>
          </Card>
        </TabsContent>
      </div>
    </Tabs>
  </main>
</template>
