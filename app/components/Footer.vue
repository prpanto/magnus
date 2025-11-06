<script lang="ts" setup>
import { useForm } from "vee-validate";
import { toTypedSchema } from "@vee-validate/zod";
import * as z from "zod";

import { Button } from "@/components/ui/button";
import {
  FormControl,
  FormField,
  FormItem,
  FormMessage,
} from "@/components/ui/form";
import {
  InputGroup,
  InputGroupAddon,
  InputGroupButton,
  InputGroupInput,
} from "@/components/ui/input-group";

const formSchema = toTypedSchema(z.object({
  email: z.email(),
}));

const form = useForm({
  validationSchema: formSchema,
});

const onSubmit = form.handleSubmit((values) => {
  console.log('Form submitted!', values)
});
</script>

<template>
  <footer class="pt-10 mt-20 px-4 sm:px-10 lg:px-24 xl:px-40">
    <div class="mb-4 flex justify-between lg:items-center max-lg:flex-col gap-10">
      <div class="space-y-2">
        <Logo />

        <p class="text-sm max-w-md text-muted-foreground">From strategy to execution, we craft digital solutions that move your business forward.</p>
      </div>

      <div class="text-muted-foreground">
        <div class="space-y-1">
          <h3 class="font-semibold">Subscribe to our newsletter</h3>
          <p class="text-sm">The latest news, articles, and resources, sent to your inbox weekly.</p>
        </div>

        <div class="mt-4">
          <form @submit="onSubmit" class="w-full flex items-center gap-2">
            <FormField v-slot="{ componentField }" name="email">
              <FormItem class="w-full">                
                <FormControl>
                  <InputGroup>
                    <InputGroupInput v-bind="componentField" placeholder="Enter your email" />

                    <InputGroupAddon align="inline-end">
                      <InputGroupButton variant="default">Subscribe</InputGroupButton>
                    </InputGroupAddon>
                  </InputGroup>
                </FormControl>

                <FormMessage />
              </FormItem>
            </FormField>
          </form>
        </div>
      </div>
    </div>

    <div class="border-t py-4 text-muted-foreground">
      <p class="">Copyright {{ new Date().getFullYear() }} © <NuxtLink to="https://github.com/prpanto" target="_blank" class="text-transparent bg-clip-text bg-linear-to-r to-blue-600 from-sky-400">Pro. Pantos</NuxtLink> - All Right Reserved.</p>
    </div>
  </footer>
</template>
