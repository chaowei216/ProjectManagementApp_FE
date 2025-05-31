<template>
  <ULink :to="`/kanban/${kanban.id}`">
    <UCard>
      <h2>{{ kanban.title }}</h2>
    </UCard>
  </ULink>
</template>

<script setup lang="ts">
defineProps<{
  kanban: {
    id: string;
    title: string;
    // description: string;
    // status: string;
    // createdAt: string;
  };
}>();
</script>
