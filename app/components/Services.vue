<script lang="ts" setup>
import {
  Card,
  CardContent,
  CardDescription,
  CardTitle,
} from "@/components/ui/card";

const data = [
  {
    title: "Advertising",
    description: "We turn bold ideas into powerful digital solutions that connect, engage...",
    icon: "mdi:lightbulb",
  },
  {
    title: "Content marketing",
    description: "We help you execute your plan and deliver results.",
    icon: "mdi:format-list-text",
  },
  {
    title: "Content writing",
    description: "We help you create a marketing strategy that drives results.",
    icon: "mdi:format-list-bulleted-type",
  },
  {
    title: "Social media",
    description: "We help you build a strong social media presence and engage with your audience.",
    icon: "mdi:share-variant",
  },
];
</script>

<template>
  <section id="services" class="relative flex flex-col items-center gap-8 px-4 sm:px-12 lg:px-24 xl:px-40 pt-30">
    <NuxtImg src="images/background/image-1.png" class="absolute -top-100 -left-50 -z-1 dark:hidden" width="2000" />

    <div class="flex flex-col items-center gap-4">
      <h2 class="text-3xl sm:text-5xl font-bold">How can we help?</h2>
      <p class="max-w-lg text-center text-muted-foreground">From strategy to execution, we craft digital solutions that move your business forward.</p>
    </div>

    <div class="flex flex-col md:grid grid-cols-2 gap-4">
      <Card v-for="(item, index) in data" :key="index" class="flex justify-center">
        <CardContent class="flex flex-row items-center gap-4">
          <Icon :name="item.icon" size="32" class="text-primary" />

          <div class="space-y-2">
            <CardTitle>{{ item.title }}</CardTitle>
            <CardDescription>{{ item.description }}</CardDescription>
          </div>
        </CardContent>
      </Card>
    </div>
  </section>
</template>
