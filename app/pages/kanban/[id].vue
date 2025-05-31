<template>
  <div class="p-4">
    <h1>Kanban {{ id }}</h1>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();
const id = route.params.id;
</script>
