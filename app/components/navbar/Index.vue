<script setup lang="ts">
import { useColorMode } from "@vueuse/core";
import { Button } from "@/components/ui/button";
import { Moon, Sun, ArrowRight } from "lucide-vue-next";

const mode = useColorMode();

const navigation = [
  {
    label: "Home",
    to: '#hero',
  },
  {
    label: "Services",
    to: '#services',
  },
  {
    label: "Our Work",
    to: '#our-work',
  },
  {
    label: "Team",
    to: '#team',
  },
  {
    label: "Contact Us",
    to: '#contact',
  },
];
</script>

<template>
  <div class="flex justify-between items-center px-4 sm:px-12 lg:px-24 xl:px-40 py-4 sticky top-0 z-20 backdrop-blur-xl bg-(--background)/50 dark:bg-(--background)/70">
    <Logo />

    <NavbarMenu class="hidden md:block" :navigation />
    
    <div class="flex items-center space-x-2">
      <Button variant="outline" @click="mode = mode === 'light' ? 'dark' : 'light'">
        <Moon v-if="mode === 'light'" />
        <Sun v-else />
      </Button>

      <NuxtLink to="#contact">
        <Button class="hidden md:flex items-center">
          <span>Contact Us</span>
          <ArrowRight />
        </Button>
      </NuxtLink>

      <NavbarSheet class="md:hidden" :navigation />
    </div>
  </div>
</template>
