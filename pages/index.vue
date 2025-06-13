<template>
  <div class="grid gap-8 h-screen">
    <header class="flex items-start justify-between">
      <div class="grow">
        <p>Hey Paul, welcome back!!</p>
        <h1>Dashboard</h1>
      </div>
      <div class="w-[120px] h-8 bg-neutral-300"></div>

    </header>
    <main>
      <div>
        <div class="flex gap-2">
          <button class="px-4 py-2 bg-blue-500 text-white rounded">
            Today
          </button>
          <button class="px-4 py-2 bg-gray-200 rounded">This Week</button>
          <button class="px-4 py-2 bg-gray-200 rounded">This Month</button>
        </div>
      </div>
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

<script setup></script>
