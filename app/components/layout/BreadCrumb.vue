<script setup lang="ts">
import type { BreadcrumbItem } from "@nuxt/ui";

const items: BreadcrumbItem[] = [
  {
    label: "Home",
    to: "/",
  },
  {
    label: "Components",
    to: "/components",
  },
  {
    label: "Breadcrumb",
    to: "/components/breadcrumb",
  },
];
</script>

<template>
  <UBreadcrumb :items="items" class="ml-4">
    <template #separator>
      <span class="text-muted">/</span>
    </template>
  </UBreadcrumb>
</template>
