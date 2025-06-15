<template>
  <div>
    <header
      class="flex items-center gap-2 p-4 hover:scale-[101%] transition cursor-pointer"
    >
      <p class="font-bold text-black flex items-center gap-3">
        <Icon size="30" name="tdesign:logo-cnb-filled" class="text-blue-500"/>
        Nuxt finance app</p>
    </header>
    <div class="px-4 grow">
      <div class="grid gap-2">
        <div v-for="(item, index) in items" :key="index">
          <NuxtLink
            :to="item.path"
            class="flex items-center gap-2 p-2 rounded hover:bg-gray-100 transition"
          >
            <Icon size="25" :name="item.icon" class="text-gray-300"/>
            <span class="text-gray-200">{{ item.name }}</span>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const items = ref([
  { name: "Home", path: "/", icon: "material-symbols:dashboard-outline" },
  {
    name: "About",
    path: "/about",
    icon: "mdi:about",
  },
  {
    name: "Services",
    path: "/services",
    icon: "grommet-icons:services",
  },
  { name: "Blog", path: "/blog", icon: "cib:micro-blog" },
  {
    name: "Portfolio",
    path: "/Portfolio",
    icon: "mdi:user",
  },
]);
</script>
