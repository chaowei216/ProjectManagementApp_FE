<template>
  <NuxtLink
    :to="to || '#'"
    active-class="text-blue-normal-active"
  >
    <UButton
      :class="status === 'mini' ? 'justify-center' : ''"
      :icon="icon"
      variant="ghost"
      color="neutral"
      class="w-full hover:bg-yellow-light hover:text-blue-dark transition-all"
    >
      <span
        class="line-clamp-1 overflow-ellipsis text-left"
        v-if="status !== 'mini'"
      >
        {{ label }}
      </span>
    </UButton>
  </NuxtLink>
</template>

<script setup lang="ts">
type SidebarItem = {
  label: string;
  icon: string;
  to?: string;
  status: string;
};
const { to, label, icon, status } = defineProps<SidebarItem>();
</script>
