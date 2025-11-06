<script lang="ts" setup>
import {
  Card,
  CardContent,
  CardDescription,
  CardTitle,
} from "@/components/ui/card";
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";

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
      <Card v-for="team in data" :key="team.name" class="flex justify-center">
        <CardContent class="flex flex-row items-center gap-4">
          <Avatar>
            <AvatarImage :src="team.avatar" :alt="team.name" class="object-cover" />
          </Avatar>

          <div class="space-y-2">
            <CardTitle>{{ team.name }}</CardTitle>
            <CardDescription>{{ team.major }}</CardDescription>
          </div>
        </CardContent>
      </Card>
    </div>
  </section>
</template>
