<script setup lang="ts">
import type { TabsItem } from "@nuxt/ui";

const items = [
  {
    label: "Table",
    icon: "i-lucide-table",
    slot: "table" as const,
  },
  {
    label: "Kanban",
    icon: "i-lucide-kanban",
    slot: "kanban" as const,
  },
  {
    label: "Metrics",
    icon: "i-lucide-bar-chart",
    slot: "metrics" as const,
  },
  {
    label: "Members",
    icon: "i-lucide-users",
    slot: "members" as const,
  },
] satisfies TabsItem[];
</script>

<template>
  <UTabs
    :items="items"
    variant="link"
    class="gap-4 w-full flex-1 h-full"
    :ui="{ trigger: 'justify-start text-sm pl-3 gap-2', content: 'h-full' }"
  >
    <template #table>
      <ProjectTableView />
    </template>

    <template #kanban>
      <ProjectKanbanView />
    </template>

    <template #metrics>
      <ProjectMetricView />
    </template>

    <template #members>
      <ProjectMemberView />
    </template>
  </UTabs>
</template>
