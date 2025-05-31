<script setup lang="ts">
import * as z from "zod";
import type { FormSubmitEvent } from "@nuxt/ui";

definePageMeta({
  layout: "blank",
});

const schema = z.object({
  email: z.string().email("Invalid email"),
  password: z.string().min(8, "Must be at least 8 characters"),
});

type Schema = z.output<typeof schema>;
const showPassword = ref(false);

const state = reactive<Partial<Schema>>({
  email: "someone@email.com",
  password: "somepassword",
});

const toast = useToast();
const { login } = useAuthStore();
async function onSubmit(event: FormSubmitEvent<Schema>) {
  toast.add({
    title: "Success",
    description: "The form has been submitted.",
    color: "success",
  });
  console.log(event.data);
}

const handleLogin = () => {
  login("", "");
  navigateTo("/");
};
</script>

<template>
  <div class="flex items-center justify-center w-full min-h-dvh">
    <UCard class="w-full max-w-md">
      <template #header>
        <h3 class="text-2xl font-bold">Login</h3>
        <p class="text-sm text-gray-500">
          Please sign-in to your account and start the adventure
        </p>
      </template>
      <UForm
        :schema="schema"
        :state="state"
        class="space-y-4"
        @submit="handleLogin"
      >
        <UFormField label="Email" name="email">
          <UInput v-model="state.email" class="w-full" />
        </UFormField>

        <UFormField label="Password" name="password">
          <div class="relative">
            <UInput
              v-model="state.password"
              :type="showPassword ? 'text' : 'password'"
              class="w-full"
            >
              <template #trailing>
                <UButton
                  variant="link"
                  @click="showPassword = !showPassword"
                  :icon="
                    showPassword ? 'i-heroicons-eye-slash' : 'i-heroicons-eye'
                  "
                />
              </template>
            </UInput>
          </div>
        </UFormField>

        <div class="text-left">
          <UButton variant="link" class="text-blue-normal font-light">
            Forgot password?
          </UButton>
        </div>
        <UButton type="submit" class="w-full justify-center"> Submit </UButton>
      </UForm>
    </UCard>
  </div>
</template>
