<template>
  <div class="bg-[#192030] sticky top-0 z-50">
    <div
      class="flex lg:hidden z-50 items-center justify-between p-4 w-full h-full"
    >
      <p class="font-bold">Nuxt Finance App</p>
      <Icon
        class="z-50 cursor-pointer left-2 top-2 text-white"
        size="30"
        name="material-symbols:menu"
        @click="open = !open"
      />
      <div
        v-if="open"
        class="fixed top-0 left-0 w-full h-screen bg-white z-[999]"
      >
        <Icon
          class="absolute top-4 right-4 cursor-pointer"
          size="30"
          name="material-symbols:close"
          @click="open = false"
        />
        <SidebarMenu />
      </div>
    </div>
    <div class="hidden lg:flex w-[300x] h-screen flex flex-col justify-between">
      <SidebarMenu />
      <div class="flex items-center p-2">
        <Icon
          size="30"
          name="material-symbols:settings"
          class="cursor-pointer m-4 text-gray-200"
        />
        <p class="text-gray-200">Settings</p>
      </div>
    </div>
  </div>
</template>

<script setup>
const open = ref(false);
</script>
