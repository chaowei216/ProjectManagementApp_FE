<!-- <script setup lang="ts">
  const router = useRouter();
  definePageMeta({
    layout: "no-sidebar",
  });
</script>

<template>
  <div class="flex w-full justify-center items-center gap-2">
    <UCard @click="router.push('/projects')">
      <template #header>
        <h1 class="font-bold">Project</h1>
      </template>
      <p>
        Manage your projects and tasks
      </p>
    </UCard>
    <UCard @click="router.push('/kanban')">
      <template #header>
        <h1 class="font-bold">Kanban</h1>
      </template>
      <p>
        Manage your projects and tasks
      </p>
    </UCard>
  </div>
</template> -->

<template>
  <NuxtLayout name="default">
    <template #header>
      <Header>
        <template #header-left>
          <!-- <h1 class="text-lg font-semibold">/projects</h1> -->
        </template>
      </Header>
    </template>
    <template #sidebar>
      <Sidebar :navigation-links="PROJECT_SIDEBAR_LINKS" />
    </template>
    <div class="flex-1 p-4 space-y-6">
      <div>
        <h3 class="font-medium mb-3 mt-4">Projects Group 1</h3>
        <div class="flex gap-4">
          <div class="flex-1 grid grid-cols-3 gap-3 pl-2">
            <ProjectListItem :project="{ id: '1', name: 'Project Demo' }" />
            <ProjectListItem :project="{ id: '2', name: 'Project 2' }" />
            <ProjectListItem :project="{ id: '3', name: 'Project 3' }" />
          </div>
        </div>
      </div>

      <div>
        <h3 class="font-medium mb-3 mt-4">Projects Group 2</h3>
        <div class="flex gap-4">
          <div class="flex-1 grid grid-cols-3 gap-3 pl-2">
            <ProjectListItem :project="{ id: '1', name: 'Project Demo' }" />
            <ProjectListItem :project="{ id: '2', name: 'Project 2' }" />
            <ProjectListItem :project="{ id: '3', name: 'Project 3' }" />
            <ProjectListItem :project="{ id: '4', name: 'Project 4' }" />
          </div>
        </div>
      </div>

      <div>
        <h3 class="font-medium mb-3 mt-4">Projects Group 3</h3>
        <div class="flex gap-4">
          <div class="flex-1 grid grid-cols-3 gap-3 pl-2">
            <ProjectListItem :project="{ id: '1', name: 'Project Demo' }" />
            <ProjectListItem :project="{ id: '2', name: 'Project 2' }" />
          </div>
        </div>
      </div>
    </div>
  </NuxtLayout>
</template>

<script setup lang="ts">
definePageMeta({
  layout: false,
});
</script>
