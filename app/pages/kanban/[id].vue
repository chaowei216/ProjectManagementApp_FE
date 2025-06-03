<template>
  <div>
    <h1>Kanban {{ id }}</h1>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();
const id = route.params.id;
</script>
