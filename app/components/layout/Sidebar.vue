<template>
  <div
    v-if="sideBarStatus !== 'hide'"
    class="p-4 bg-blue-light flex flex-col justify-between h-full transition-all"
    :class="sideBarStatus === 'mini' ? 'w-[80px]' : 'w-[200px]'"
  >
    <div>
      <div class="flex items-center justify-between mb-8">
        <NuxtLink to="/">
          <div class="text-lg font-bold px-4 text-blue-normal-active">
            {{ sideBarStatus === "mini" ? "S" : "SPM" }}
          </div>
        </NuxtLink>
        <UButton
          :variant="sideBarStatus === 'mini' ? 'outline' : 'ghost'"
          icon="i-lucide-panel-left"
          class="ml-auto bg-blue-light relative z-30"
          @click="toggleSidebar"
        />
      </div>

      <nav>
        <ul class="space-y-2">
          <li>
            <UButton
              variant="ghost"
              class="w-full text-xs text-muted-foreground"
            >
              <span class="line-clamp-1 overflow-ellipsis text-left">
                {{ sideBarStatus === "mini" ? "" : "Main" }}
              </span>
            </UButton>
          </li>
          <li v-for="link in mainItems" :key="link.to">
            <SidebarItem
              :to="link.to"
              :status="sideBarStatus"
              :icon="link.icon"
              :label="link.label"
            />
          </li>

          <USeparator />

          <UCollapsible :unmount-on-hide="false" default-open>
            <li>
              <UButton
                variant="ghost"
                class="w-full text-xs text-muted-foreground flex items-center mb-1"
                :class="
                  sideBarStatus === 'mini'
                    ? 'justify-center'
                    : 'justify-between'
                "
              >
                <span
                  class="line-clamp-1 overflow-ellipsis text-left font-semibold"
                  v-if="sideBarStatus !== 'mini'"
                >
                  Recent
                </span>
                <UIcon name="i-lucide-chevron-down" class="size-5" />
              </UButton>
            </li>

            <template #content>
              <li v-for="link in recentItems" :key="link.to">
                <SidebarItem
                  :to="link.to"
                  :status="sideBarStatus"
                  :icon="link.icon"
                  :label="link.label"
                />
              </li>
            </template>
          </UCollapsible>

          <UCollapsible :unmount-on-hide="false">
            <li>
              <UButton
                variant="ghost"
                class="w-full text-xs text-muted-foreground flex items-center mb-1"
                :class="
                  sideBarStatus === 'mini'
                    ? 'justify-center'
                    : 'justify-between'
                "
              >
                <span
                  class="line-clamp-1 overflow-ellipsis text-left font-semibold"
                  v-if="sideBarStatus !== 'mini'"
                >
                  Workspace A
                </span>
                <UIcon name="i-lucide-chevron-down" class="size-5" />
              </UButton>
            </li>

            <template #content>
              <li v-for="link in recentItems" :key="link.to">
                <SidebarItem
                  :to="link.to"
                  :status="sideBarStatus"
                  :icon="link.icon"
                  :label="link.label"
                />
              </li>
            </template>
          </UCollapsible>

          <UCollapsible :unmount-on-hide="false">
            <li>
              <UButton
                variant="ghost"
                class="w-full text-xs text-muted-foreground flex items-center mb-1"
                :class="
                  sideBarStatus === 'mini'
                    ? 'justify-center'
                    : 'justify-between'
                "
              >
                <span
                  class="line-clamp-1 overflow-ellipsis text-left font-semibold"
                  v-if="sideBarStatus !== 'mini'"
                >
                  Workspace B
                </span>
                <UIcon name="i-lucide-chevron-down" class="size-5" />
              </UButton>
            </li>

            <template #content>
              <li v-for="link in recentItems" :key="link.to">
                <SidebarItem
                  :to="link.to"
                  :status="sideBarStatus"
                  :icon="link.icon"
                  :label="link.label"
                />
              </li>
            </template>
          </UCollapsible>
        </ul>
      </nav>
    </div>

    <UPopover
      :content="{
        side: 'bottom',
        align: 'start',
      }"
    >
      <div
        class="px-2 py-1 text-sm flex items-center gap-2 border border-gray-200 rounded-lg bg-white"
      >
        <UAvatar size="sm"> C </UAvatar>
        <span
          v-if="sideBarStatus === 'extend'"
          class="font-semibold flex-1 text-blue-normal-active"
          >Username</span
        >
        <UButton
          v-if="sideBarStatus === 'extend'"
          variant="ghost"
          icon="i-lucide-chevron-down"
        />
      </div>

      <template #content>
        <div class="px-4 py-2 rounded-sm w-[200px]">
          <UButton variant="ghost" color="neutral" class="w-full">
            <UIcon name="i-lucide-user" />
            Profile
          </UButton>
          <UButton variant="ghost" color="error" class="w-full">
            <UIcon name="i-lucide-log-out" />
            Logout
          </UButton>
        </div>
      </template>
    </UPopover>
  </div>
</template>

<script setup lang="ts">
import { USeparator } from "#components";

const sideBarStatus = ref("extend");
type SidebarItem = {
  label: string;
  icon: string;
  to: string;
};
defineProps<{
  navigationLinks?: SidebarItem[];
}>();

const mainItems = ref<SidebarItem[]>([
  {
    label: "Workspace",
    icon: "i-lucide-home",
    to: "/workspace",
  },
]);

const recentItems = ref<SidebarItem[]>([
  {
    label: "Project 1",
    icon: "i-lucide-folder",
    to: "/projects/1",
  },
  {
    label: "Project 2",
    icon: "i-lucide-folder",
    to: "/projects/2",
  },
  {
    label: "Project 3",
    icon: "i-lucide-folder",
    to: "/projects/3",
  },
]);

const toggleSidebar = () => {
  sideBarStatus.value = sideBarStatus.value === "mini" ? "extend" : "mini";
};
</script>
