<script setup lang="ts">
import { useForm } from "vee-validate";
import { toTypedSchema } from "@vee-validate/zod";
import * as z from "zod";
import { Button } from "@/components/ui/button";
import {
  FormControl,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from "@/components/ui/form";
import { Input } from "@/components/ui/input";
import Textarea from "@/components/ui/textarea/Textarea.vue";
import { ArrowRight } from "lucide-vue-next";

const formSchema = toTypedSchema(z.object({
  name: z.string().min(3).max(100),
  email: z.email(),
  message: z.string().min(10).max(255),
}))

const form = useForm({
  validationSchema: formSchema,
})

const onSubmit = form.handleSubmit((values) => {
  console.log("Form submitted!", values)
})
</script>

<template>
  <section id="contact" class="relative flex flex-col items-center gap-8 px-4 sm:px-12 lg:px-24 xl:px-40 pt-30">
    <div class="flex flex-col items-center gap-4">
      <h2 class="text-3xl sm:text-5xl font-bold">Reach out to us</h2>
      <p class="max-w-lg text-center text-muted-foreground">From strategy to execution, we craft digital solutions that move your business forward.</p>
    </div>

    <form @submit="onSubmit" class="max-w-2xl w-full space-y-6">
      <div class="max-w-2xl w-full space-y-4">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 max-w-2xl w-full">
          <FormField v-slot="{ componentField }" name="name">
            <FormItem>
              <FormLabel>Name</FormLabel>

              <FormControl>
                <Input type="text" placeholder="Enter your name" v-bind="componentField" />
              </FormControl>

              <FormMessage />
            </FormItem>
          </FormField>

          <FormField v-slot="{ componentField }" name="email">
            <FormItem>
              <FormLabel>Name</FormLabel>

              <FormControl>
                <Input type="text" placeholder="Enter your email" v-bind="componentField" />
              </FormControl>

              <FormMessage />
            </FormItem>
          </FormField>
        </div>

        <FormField v-slot="{ componentField }" name="message">
          <FormItem>
            <FormLabel>Message</FormLabel>

            <FormControl>
              <Textarea
                placeholder="Ender your message"
                v-bind="componentField"
              />
            </FormControl>

            <FormMessage />
          </FormItem>
        </FormField>
      </div>

      <Button type="submit">
        Submit
        <ArrowRight />
      </Button>
    </form>
  </section>
</template>
