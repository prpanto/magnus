<script setup lang="ts">
import type { NavigationMenuRootProps } from "reka-ui";
import {
  NavigationMenu,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
} from "@/components/ui/navigation-menu";


defineProps<{
  props?: NavigationMenuRootProps;
  navigation: {
    label: string;
    to: string;
  }[];
}>();
</script>

<template>
  <NavigationMenu v-bind="props">
    <NavigationMenuList class="gap-2 space-x-0 data-[orientation=vertical]:flex-col data-[orientation=vertical]:items-start">
      <NavigationMenuItem v-for="item in navigation" :key="item.to">
        <NavigationMenuLink asChild>
          <NuxtLink :to="item.to">{{ item.label }}</NuxtLink>
        </NavigationMenuLink>
      </NavigationMenuItem>
    </NavigationMenuList>
  </NavigationMenu>
</template>
