<script lang="ts" setup>
import {
  Card,
  CardContent,
  CardDescription,
  CardTitle,
} from "@/components/ui/card";

const data = [
  {
    avatar: "images/avatars/01.avif",
    name: "James Walker",
    major: "CEO & Founder",
  },
  {
    avatar: "images/avatars/02.avif",
    name: "Ashley Bennett",
    major: "Marketing & Sales",
  },
  {
    avatar: "images/avatars/03.avif",
    name: "Jessica Morgan",
    major: "Senior writer",
  },
  {
    avatar: "images/avatars/04.avif",
    name: "Ryan Mitchell",
    major: "Content marketer",
  },
];
</script>

<template>
  <section id="team" class="relative flex flex-col items-center gap-8 px-4 sm:px-12 lg:px-24 xl:px-40 pt-30">
    <div class="flex flex-col items-center gap-4">
      <h2 class="text-3xl sm:text-5xl font-bold">Meet the team</h2>
      <p class="max-w-lg text-center text-muted-foreground">A passionate team of digital experts dedicated to your brands success.</p>
    </div>

    <div class="flex flex-col md:grid grid-cols-2 gap-4">
      <Card v-for="item in data" :key="item.name" class="flex justify-center">
        <CardContent class="flex flex-row items-center gap-4">
          <NuxtImg :src="item.avatar" width="40" height="40" class="rounded-full" />

          <div class="space-y-2">
            <CardTitle>{{ item.name }}</CardTitle>
            <CardDescription>{{ item.major }}</CardDescription>
          </div>
        </CardContent>
      </Card>
    </div>
  </section>
</template>
