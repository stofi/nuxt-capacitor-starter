<template>
  <div class="flex flex-col h-screen">
    <header class="border-b border-gray-200 dark:border-gray-800 p-4 flex items-center justify-between">
      <h1 class="text-lg font-bold">
        My App
      </h1>
      <UButton
        icon="i-lucide-moon"
        color="neutral"
        variant="ghost"
        @click="$colorMode.preference = $colorMode.value === 'dark' ? 'light' : 'dark'"
      />
    </header>

    <main class="flex-1 overflow-auto">
      <div class="p-4">
        <slot />
      </div>
    </main>

    <nav class="border-t border-gray-200 dark:border-gray-800 bg-white dark:bg-gray-950">
      <div class="flex items-center justify-around p-2">
        <NuxtLink
          to="/"
          class="flex flex-col items-center gap-1 px-4 py-2 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-800"
        >
          <UIcon
            name="i-lucide-home"
            class="text-xl"
          />
          <span class="text-xs">Home</span>
        </NuxtLink>
        <NuxtLink
          to="/settings"
          class="flex flex-col items-center gap-1 px-4 py-2 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-800"
        >
          <UIcon
            name="i-lucide-settings"
            class="text-xl"
          />
          <span class="text-xs">Settings</span>
        </NuxtLink>
      </div>
    </nav>
  </div>
</template>
