<template>
  <div class="min-w-[300px] flex flex-col bg-gradient-to-b from-white to-gray-100 p-4 rounded-sm" :class="classname">
    <div class="flex items-center gap-2 mb-4">
      <div class="w-5 h-5 rounded-sm" :style="{ backgroundColor: color }"></div>
      <Heading :title="title" class="font-medium" size="sm" />
    </div>
    <div
      class="flex-1 flex flex-col justify-between "
    >
      <div class="overflow-y-auto hide-scrollbar max-h-[460px] p-px"><slot /></div>
      <div class="mt-4">
        <UButton variant="outline" size="sm" color="neutral">
          <Icon name="lucide:plus" class="w-4 h-4" />
          Add Card
        </UButton>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const {
  title,
  color,
  class: classname,
} = defineProps<{
  title: string;
  color: string;
  class: string;
}>();
</script>
