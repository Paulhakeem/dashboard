<template>
  <div class="grid gap-4">
    <header class="flex items-start justify-between">
      <div class="grow">
        <p>Hey Paul, welcome back!!</p>
        <h1>Dashboard</h1>
      </div>
      <div class="w-[120px] h-8 bg-neutral-300"></div>
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
        <div class="mt-4">
          <div class="h-64 bg-gray-200 rounded-lg"></div>
        </div>
      </section>
    </main>
    <footer>
      <div class="grid grid-cols-3 md:grid-cols-3 gap-4 mt-4">
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
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";

const list = ref([
  { name: "Today", component: resolveComponent("TabsToday") },
  { name: "Week", component: resolveComponent("TabsWeek") },
  { name: "Month", component: resolveComponent("TabsMonth") },
]);
</script>
