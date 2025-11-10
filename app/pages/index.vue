<template>
  <div>
    <UCard>
      <template #header>
        <h3 class="text-lg font-semibold">
          Welcome
        </h3>
      </template>

      <p class="text-gray-600 dark:text-gray-400">
        This is a simple starter template with Nuxt, Nuxt UI, and Capacitor.
      </p>

      <div class="mt-4 grid grid-cols-1 md:grid-cols-3 gap-4">
        <UCard>
          <div class="flex items-center gap-3">
            <UIcon
              name="i-lucide-box"
              class="text-2xl"
            />
            <div>
              <p class="font-semibold">
                Nuxt 4
              </p>
              <p class="text-sm text-gray-500">
                Latest version
              </p>
            </div>
          </div>
        </UCard>

        <UCard>
          <div class="flex items-center gap-3">
            <UIcon
              name="i-lucide-palette"
              class="text-2xl"
            />
            <div>
              <p class="font-semibold">
                Nuxt UI
              </p>
              <p class="text-sm text-gray-500">
                Component library
              </p>
            </div>
          </div>
        </UCard>

        <UCard>
          <div class="flex items-center gap-3">
            <UIcon
              name="i-lucide-smartphone"
              class="text-2xl"
            />
            <div>
              <p class="font-semibold">
                Capacitor
              </p>
              <p class="text-sm text-gray-500">
                iOS ready
              </p>
            </div>
          </div>
        </UCard>
      </div>
    </UCard>

    <div class="mt-6 grid grid-cols-1 md:grid-cols-2 gap-6">
      <UCard>
        <template #header>
          <h4 class="font-semibold">
            Quick Actions
          </h4>
        </template>
        <div class="space-y-2">
          <UButton
            block
            color="primary"
            variant="soft"
          >
            Action 1
          </UButton>
          <UButton
            block
            color="primary"
            variant="soft"
          >
            Action 2
          </UButton>
        </div>
      </UCard>

      <UCard>
        <template #header>
          <h4 class="font-semibold">
            Stats
          </h4>
        </template>
        <div class="space-y-3">
          <div class="flex justify-between">
            <span class="text-gray-600 dark:text-gray-400">Items</span>
            <span class="font-semibold">42</span>
          </div>
          <div class="flex justify-between">
            <span class="text-gray-600 dark:text-gray-400">Active</span>
            <span class="font-semibold">12</span>
          </div>
        </div>
      </UCard>
    </div>
  </div>
</template>
