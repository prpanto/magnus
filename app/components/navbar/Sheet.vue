<script setup lang="ts">
import { Button } from "@/components/ui/button";
import {
  Sheet,
  SheetTrigger,
  SheetContent,
} from "@/components/ui/sheet";
import { Menu } from "lucide-vue-next";
import Logo from "@/components/Logo.vue";
import { ArrowRight } from "lucide-vue-next";


defineProps<{
  navigation: {
    label: string;
    to: string;
  }[];
}>();
</script>

<template>
  <Sheet class="md:hidden">
    <SheetTrigger asChild class="md:hidden">
      <Button variant="outline" size="icon">
        <Menu />
      </Button>
    </SheetTrigger>

    <SheetContent class="px-4 py-2">
      <Logo />
      <NavbarMenu :navigation orientation="vertical" />

      <div class="mt-4">
        <Button class="w-full flex items-center">
          <span>Contact Us</span>
          <ArrowRight />
        </Button>
      </div>
    </SheetContent>
  </Sheet>
</template>
