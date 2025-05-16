<script setup>
const store = useCounterStore();
const { count, name } = storeToRefs(store);
const { increment } = store;
</script>

<template>
  <UButton @click="increment" class="ml-2">Count: {{ count }} </UButton>
  <p>Name: {{ name }}</p>
</template>
