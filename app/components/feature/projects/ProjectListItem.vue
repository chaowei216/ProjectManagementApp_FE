<template>
  <NuxtLink :to="`/projects/${project.id}`">
    <UCard :ui="{ body: 'sm:p-3' }">
      <div class="flex items-center gap-2">
        <img
          src="https://picsum.photos/id/29/400"
          alt="Project"
          class="size-12 rounded-sm"
          width="48"
          height="48"
        />
        <div>
          <h3 class="text-sm">{{ project.name }}</h3>
          <p class="text-xs text-gray-500">
            Lorem, ipsum dolor sit amet consectetur odio.
          </p>
        </div>
      </div>
    </UCard>
  </NuxtLink>
</template>

<script setup lang="ts">
defineProps<{
  project: {
    id: string;
    name: string;
  };
}>();
</script>
