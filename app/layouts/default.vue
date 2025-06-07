<script setup lang="ts"></script>

<template>
  <div class="flex flex-col min-h-dvh">
    <div class="flex-1 flex">
      <div>
        <slot name="sidebar">
          <Sidebar :navigation-links="[]" />
        </slot>
      </div>
      <div class="flex-1 flex flex-col h-screen overflow-y-auto relative">
        <div class="sticky top-0 z-20 bg-white">
          <slot name="header">
            <Header />
          </slot>
        </div>

        <div class="flex-1 p-4 flex flex-col">
          <slot />
        </div>
      </div>
    </div>

    <!-- <Footer /> -->
  </div>
</template>
