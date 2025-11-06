<script setup lang="ts">
import Badge from '@/components/ui/badge/Badge.vue';
</script>

<template>
  <section id="hero" class="flex flex-col items-center gap-6 py-20 px-4 sm:px-12 lg:px-24 xl:px-40 w-full overflow-hidden">
    <Badge class="py-1 gap-2 rounded-full">
      <div class="flex -space-x-1.5">
        <NuxtImg
          class="ring-background rounded-full ring-1"
          src="images/avatars/01.avif"
          width="25"
          height="25"
          alt="Avatar 01"
        />
        <NuxtImg
          class="ring-background rounded-full ring-1"
          src="images/avatars/02.avif"
          width="25"
          height="25"
          alt="Avatar 02"
        />
        <NuxtImg
          class="ring-background rounded-full ring-1"
          src="images/avatars/03.avif"
          width="25"
          height="25"
          alt="Avatar 03"
        />
        <NuxtImg
          class="ring-background rounded-full ring-1"
          src="images/avatars/04.avif"
          width="25"
          height="25"
          alt="Avatar 04"
        />
      </div>

      Trusted by 10k+ people
    </Badge>

    <div class="flex flex-col items-center gap-4 text-center">
      <h1 class="text-4xl sm:text-5xl md:text-6xl xl:text-[84px] font-bold xl:leading-[95px] max-w-5xl">
        Turning imagination into
        <span class="text-primary">digital</span>
        impact.
      </h1>

      <p class="text-sm sm:text-lg font-medium text-muted-foreground max-w-4/5 sm:max-w-lg">Creating meaningful connections and turning big ideas into interactive digital experiences.</p>
    </div>

    <div class="relative">
      <NuxtImg src="images/hero/image1.jpg" alt="Hero Image" class="rounded-xl" width="1000" />
      <div class="pointer-events-none absolute -top-30 -left-10 size-120 rounded-full bg-primary/30 blur-2xl -z-1"></div>
      <div class="pointer-events-none absolute -top-20 -right-10 size-120 rounded-full bg-primary/30 blur-2xl -z-1"></div>
      <div class="pointer-events-none absolute -top-25 -right-30 size-120 rounded-full bg-accent/25 blur-2xl -z-1"></div>
    </div>
  </section>
</template>
