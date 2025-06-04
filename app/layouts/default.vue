<script setup lang="ts"></script>

<template>
  <div class="flex flex-col min-h-dvh">
    <div class="flex-1 flex">
      <div>
        <slot name="sidebar">
          <Sidebar :navigation-links="[]" />
        </slot>
      </div>
      <div class="flex-1 flex flex-col">
        <slot name="header">
          <Header />
        </slot>

        <div class="flex-1 p-4 flex">
          <slot />
        </div>
      </div>
    </div>

    <!-- <Footer /> -->
  </div>
</template>
