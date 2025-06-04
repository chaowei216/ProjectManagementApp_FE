<script setup lang="ts">
import { UPopover } from "#components";

const authStore = useAuthStore();
const { isAuthenticated } = storeToRefs(authStore);
const { logout } = authStore;
const onLoginClick = () => {
  navigateTo("/login");
};
const onLogoutClick = () => {
  logout();
  navigateTo("/login");
};

const searchInput = ref();

onMounted(() => {
  window.addEventListener("keydown", handleKeyDown);
});

onUnmounted(() => {
  window.removeEventListener("keydown", handleKeyDown);
});

const handleKeyDown = (e: KeyboardEvent) => {
  if ((e.ctrlKey || e.metaKey) && e.key.toLowerCase() === "k") {
    e.preventDefault();
    searchInput.value?.input?.focus();
  }
};
</script>

<template>
  <Container class="py-2 flex w-full border-b border-b-blue-light items-center">
    <div class="flex items-center gap-2">
      <UButton variant="ghost" @click="navigateTo('/')">
        <UIcon name="i-lucide-arrow-left" />
      </UButton>
      <UButton variant="ghost" @click="navigateTo('/')">
        <UIcon name="i-lucide-arrow-right" />
      </UButton>

      <BreadCrumb />

      <slot name="header-left" />
    </div>
    <div class="flex items-center justify-end gap-2 flex-1">
      <slot name="header-right" />
      <UInput
        :ref="searchInput"
        icon="i-lucide-search"
        placeholder="Search..."
        class="w-64"
      >
        <template #trailing>
          <UKbd value="Ctrl + K" variant="subtle" />
        </template>
      </UInput>
      <UPopover :content="{ side: 'bottom', align: 'end' }">
        <UButton variant="ghost" class="rounded-full">
          <UChip color="error" class="p-px">
            <UIcon size="18px" name="i-lucide-bell" />
          </UChip>
        </UButton>

        <template #content>
          <div class="w-[320px] p-4 rounded-sm">
            <div>
              <div class="flex justify-between items-center">
                <span class="text-sm font-medium">Notifications</span>
                <UButton variant="ghost" size="sm">
                  <UIcon name="i-lucide-check" /> Mark all as read
                </UButton>
              </div>
              <ul class="mt-2 text-xs space-y-2">
                <li
                  class="hover:bg-yellow-light-active transition-all rounded-sm px-2 py-1"
                >
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Nihil, odit.
                </li>
                <li
                  class="hover:bg-yellow-light-active transition-all rounded-sm px-2 py-1"
                >
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet
                  omnis est consequatur delectus. Commodi.
                </li>
                <li
                  class="hover:bg-yellow-light-active transition-all rounded-sm px-2 py-1"
                >
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Quisquam, quos.
                </li>
              </ul>
            </div>
            <div></div>
          </div>
        </template>
      </UPopover>
    </div>
  </Container>
</template>
