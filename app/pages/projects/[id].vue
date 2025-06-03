<template>
  <div class="w-full">
    <div class="-mt-2 relative">
      <div class="absolute top-0 right-0 z-10">
        <ProjectDetailAction />
      </div>
      <ProjectTabs />
    </div>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();
</script>
