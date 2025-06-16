<template>
  <div>
    <header
      class="flex items-center gap-2 p-4 hover:scale-[101%] transition cursor-pointer"
    >
      <h5 class="font-bold text-gray-200 flex items-center gap-3">
        <Icon size="30" name="tdesign:logo-cnb-filled" class="text-blue-500" />
        Nuxt finance app
      </h5>
    </header>
    <div class="px-4 grow">
      <div class="grid gap-2">
        <div v-for="(item, index) in items" :key="index">
          <NuxtLink
            :to="item.path"
            class="flex items-center gap-2 p-2 rounded hover:bg-gray-600 transition"
          >
            <Icon size="25" :name="item.icon" class="text-gray-300" />
            <span class="text-gray-200">{{ item.name }}</span>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const items = ref([
  { name: "Dashboard", path: "/", icon: "material-symbols:dashboard-outline" },
  {
    name: "Budgeting",
    path: "/budgeting",
    icon: "healthicons:low-income-level",
  },
  {
    name: "Income",
    path: "/income",
    icon: "bi:graph-up-arrow",
  },
  { name: "Expenses", path: "/expenses", icon: "bi:graph-down-arrow" },
  { name: "Investments", path: "/investments", icon: "uis:graph-bar" },
  {
    name: "Debts",
    path: "/debts",
    icon: "covid:graph-death-rate-stable",
  },
]);
</script>
