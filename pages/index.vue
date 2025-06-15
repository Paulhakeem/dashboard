<template>
  <div class="grid gap-8">
    <header class="flex items-start justify-between">
      <div class="grow">
        <p>Hey Paul, welcome back!!</p>
        <h1>Dashboard</h1>
      </div>
      <div>
        <Button class="bg-[#192030] cursor-pointer">Profile</Button>
      </div>
    </header>
    <main>
      <Tabs default-value="today" class="w-[400px]">
        <TabsList>
          <TabsTrigger
            v-for="(tab, index) in list"
            :key="index"
            :value="tab.name"
            class="cursor-pointer"
          >
            {{ tab.name }}
          </TabsTrigger>
        </TabsList>
        <TabsContent
          v-for="(tab, index) in list"
          :key="index"
          :value="tab.name"
        >
          <component :is="tab.component" />
        </TabsContent>
      </Tabs>
      <section>
        <div class="grid grid-cols-2 mt-4 gap-8">
          <div class="h-64">
            <ChartsDonutChart/>
          </div>
          <div class="h-64">
            <div class="h-64">
              <ChartsBarChart />
            </div>
          </div>
        </div>
      </section>
    </main>
    <footer>
      <div class="grid grid-cols-3 md:grid-cols-3 gap-4 mt-20">
        <div class="p-4 bg-white rounded-lg shadow">
          <h2 class="text-lg font-semibold">Card 1</h2>
          <p>Content for card 1.</p>
        </div>
        <div class="p-4 bg-white rounded-lg shadow">
          <h2 class="text-lg font-semibold">Card 2</h2>
          <p>Content for card 2.</p>
        </div>
        <div class="p-4 bg-white rounded-lg shadow">
          <h2 class="text-lg font-semibold">Card 3</h2>
          <p>Content for card 3.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ChartsBarChart } from "#components";
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";

const list = ref([
  { name: "Today", component: resolveComponent("TabsToday") },
  { name: "Week", component: resolveComponent("TabsWeek") },
  { name: "Month", component: resolveComponent("TabsMonth") },
]);

const RevenueData = [
  { month: "January", desktop: 186, mobile: 80 },
  { month: "February", desktop: 305, mobile: 200 },
  { month: "March", desktop: 237, mobile: 120 },
  { month: "April", desktop: 73, mobile: 190 },
  { month: "May", desktop: 209, mobile: 130 },
  { month: "June", desktop: 214, mobile: 140 },
];
const RevenueCategoriesMultple = {
  desktop: { name: "Desktop", color: "#3b82f6" },
  mobile: { name: "Mobile", color: "#22c55e" },
};

const yFormatter = (i) => `${RevenueData[i]?.month}`;
</script>
