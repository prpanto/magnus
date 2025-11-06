<script lang="ts" setup>
import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

const data = [
  {
    image: "images/work/mobile_app.png",
    title: "Mobile app marketing",
    description: "We turn bold ideas into powerful digital solutions that connect, engage...",
  },
  {
    image: "images/work/dashboard_management.png",
    title: "Dashboard management",
    description: "We help you execute your plan and deliver results.",
  },
  {
    image: "images/work/fitness_app.png",
    title: "Fitness app promotion",
    description: "We help you create a marketing strategy that drives results.",
  },
];
</script>

<template>
  <section id="our-work" class="relative flex flex-col items-center gap-8 px-4 sm:px-12 lg:px-24 xl:px-40 pt-30">
    <div class="flex flex-col items-center gap-4">
      <h2 class="text-3xl sm:text-5xl font-bold">Our latest work</h2>
      <p class="max-w-lg text-center text-muted-foreground">From strategy to execution, we craft digital solutions that move your business forward.</p>
    </div>

    <div class="mt-8 xs:mt-14 w-full mx-auto grid md:grid-cols-2 lg:grid-cols-3 gap-x-10 gap-y-12">
      <Card
        v-for="item in data"
        :key="item.title"
        class="flex flex-col pt-0 border rounded-xl overflow-hidden shadow-none"
      >
       <CardContent class="px-0 pb-0">
          <NuxtImg
            :src="item.image"
            alt="Our Work Image"
            class="size-full object-cover"
          />
        </CardContent>

        <CardHeader>
          <CardTitle>{{ item.title }}</CardTitle>
          <CardDescription>{{ item.description }}</CardDescription>
        </CardHeader>
      </Card>
    </div>
  </section>
</template>
