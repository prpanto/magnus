<script lang="ts" setup>
const clientsLogos = [
  "images/clients/airbnb.svg",
  "images/clients/coinbase.png",
  "images/clients/google.svg",
  "images/clients/microsoft.png",
  "images/clients/rakuten.png",
  "images/clients/zoom.png"
];
</script>

<template>
  <section class="flex flex-col items-center px-4 sm:px-12 lg:px-24 xl:px-40 gap-6">
    <h3 class="font-semibold text-muted-foreground">Trusted by Leading Companies</h3>

    <div class="flex items-center justify-center flex-wrap gap-10 m-4">
      <NuxtImg
        v-for="(logo, index) in clientsLogos"
        :key="index"
        :src="logo"
        alt="Client"
        width="75"
      />
    </div>
  </section>
</template>
