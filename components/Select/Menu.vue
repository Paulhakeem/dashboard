<script setup>
import {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectLabel,
  SelectTrigger,
  SelectValue,
} from "@/components/ui/select";
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";

const year = shallowRef([
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
const selectedMonth = ref("january");
</script>

<template>
  <main>
    <Select v-model="selectedMonth">
      <SelectTrigger class="w-[130px]">
        <SelectValue />
      </SelectTrigger>
      <SelectContent>
        <SelectGroup>
          <SelectLabel>Months</SelectLabel>
          <SelectItem v-for="m in year" :key="m.value" :value="m.value">
            {{ m.month }}
          </SelectItem>
        </SelectGroup>
      </SelectContent>
    </Select>

    <!--  -->
    <Tabs v-model="selectedMonth" class=" w-screen max-w-none overflow-x-hidden mt-6">
      <div v-for="m in year" :key="m.value" class="w-full">
        <TabsContent :value="m.value">
          <Card>
            <CardContent class="space-y-2">
              <component :is="m.component" />
            </CardContent>
          </Card>
        </TabsContent>
      </div>
    </Tabs>

  </main>
</template>
