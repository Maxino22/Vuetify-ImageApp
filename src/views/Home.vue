<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <VApp>
    <!-- SIDeBAR -->
    <SideBar />
    <VMain>
      <ImageGallary />
    </VMain>
  </VApp>
</template>

<script setup>
import ImageGallary from "@/components/ImageGallary.vue";
import SideBar from "@/components/SideBar.vue";
</script>
