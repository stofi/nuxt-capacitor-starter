<template>
  <div>
    <UCard>
      <template #header>
        <h3 class="text-lg font-semibold">
          Settings
        </h3>
      </template>

      <div class="space-y-4">
        <div>
          <label class="block text-sm font-medium mb-2">Name</label>
          <UInput placeholder="Enter your name" />
        </div>

        <div>
          <label class="block text-sm font-medium mb-2">Email</label>
          <UInput
            type="email"
            placeholder="your@email.com"
          />
        </div>

        <div>
          <label class="block text-sm font-medium mb-2">Preferences</label>
          <USwitch label="Enable notifications" />
        </div>

        <div class="pt-4">
          <UButton color="primary">
            Save Changes
          </UButton>
        </div>
      </div>
    </UCard>
  </div>
</template>
