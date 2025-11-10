<script lang="ts" setup>
import {
  Card,
  CardContent,
  CardDescription,
  CardTitle,
} from "@/components/ui/card";
import { Avatar, AvatarImage } from "@/components/ui/avatar";

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
    major: "Senior Writer",
  },
  {
    avatar: "images/avatars/04.avif",
    name: "Ryan Mitchell",
    major: "Content Marketer",
  },
  {
    avatar: "images/avatars/05.avif",
    name: "Mark Brown",
    major: "Senior Writer",
  },
  {
    avatar: "images/avatars/06.avif",
    name: "Mike Gerald",
    major: "Content Marketer",
  },
];
</script>

<template>
  <section id="team" class="relative flex flex-col items-center gap-8 px-4 sm:px-12 lg:px-24 xl:px-40 pt-30">
    <div class="flex flex-col items-center gap-4">
      <h2 class="text-3xl sm:text-5xl font-bold">Meet the team</h2>
      <p class="max-w-lg text-center text-muted-foreground">A passionate team of digital experts dedicated to your brands success.</p>
    </div>

    <div class="flex flex-col md:grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      <Card v-for="member in data" :key="member.name" class="flex justify-center">
        <CardContent class="flex flex-row items-center gap-4">
          <Avatar>
            <AvatarImage :src="member.avatar" :alt="member.name" class="object-cover" />
          </Avatar>

          <div class="space-y-2">
            <CardTitle>{{ member.name }}</CardTitle>
            <CardDescription>{{ member.major }}</CardDescription>
          </div>
        </CardContent>
      </Card>
    </div>
  </section>
</template>
