<template>
  <div class="grid gap-8">
    <header class="flex items-start justify-between">
      <div class="grow">
        <p>Hey Paul, welcome back!!</p>
        <h1>Dashboard</h1>
      </div>
      <div>
        <Button class="bg-[#242632] cursor-pointer">Profile</Button>
      </div>
    </header>
    <main>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-10 mb-10">
        <div class="flex-wrap md:flex lg:flex gap-10">
          <div class="p-4 bg-[#242632] rounded-lg shadow w-64 h-24">
            <h2 class="text-sm font-semibold text-gray-200">Total Income</h2>
            <h5 class="text-2xl text-gray-200 font-bold">$12,345</h5>
          </div>
          <div class="p-4 bg-[#242632] rounded-lg shadow w-64 h-24">
            <h2 class="text-sm text-gray-200 font-semibold">New Users</h2>
            <h5 class="text-2xl font-bold text-gray-200">1,234</h5>
          </div>
        </div>
        <div>
          <ChartsLineChart />
        </div>
      </div>
      <section>
        <div
          id="charts"
          class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-[80px]"
        >
          <div class="h-64">
            <ChartsDonutChart />
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
      <div class="grid grid-cols-3 md:grid-cols-3 gap-4 pt-[150px]">
        <div class="p-4 bg-white rounded-lg shadow">
          <h2 class="text-lg font-semibold">Card 1</h2>
          <p>Content for card 1.</p>
        </div>
        <div class="p-4 bg-white rounded-lg shadow">
          <h2 class="text-lg font-semibold">Card 2</h2>
          <p>Content for card 2.</p>
        </div>
        <CardTotalCard />
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ChartsBarChart } from "#components";

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
