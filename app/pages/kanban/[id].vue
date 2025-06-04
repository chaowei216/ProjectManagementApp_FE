<template>
  <div class="flex-1 flex flex-col">
    <Heading :title="`Kanban ${id}`" size="lg" class="mb-2" />
    <USeparator />
    <div class="flex gap-4 bg-gray-50 flex-1 p-2 mt-2">
      <KanbanStage title="To Do" color="#F43F5E" class="flex-1">
        <div class="flex flex-col gap-2">
          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>

          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>

          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>

          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>

          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>
        </div>
      </KanbanStage>
      <KanbanStage title="In Progress" color="#2196F3" class="flex-1">
        <div class="flex flex-col gap-2">
          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>
  
          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>
        </div>
      </KanbanStage>
      <KanbanStage title="Done" color="#4CAF50" class="flex-1">
        <div class="flex flex-col gap-2">
          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>
  
          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p> </UCard
          ><UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>
  
          <UCard>
            Test
            <p class="text-sm text-gray-500">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi,
              veritatis!
            </p>
          </UCard>
        </div>
      </KanbanStage>
    </div>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();
const id = route.params.id;
</script>
