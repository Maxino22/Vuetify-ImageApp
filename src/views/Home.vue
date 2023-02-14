<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <VApp>
    <!-- SIDeBAR -->
    <SideBar @selectOption="onSelect" />
    <VMain>
      <ImageGallary :isWithColor="isWithColor" />
    </VMain>
  </VApp>
</template>

<script setup>
import ImageGallary from "@/components/ImageGallary.vue";
import SideBar from "@/components/SideBar.vue";
import { ref } from "vue";
const isWithColor = ref(true);

const onSelect = (isColor) => {
  isWithColor.value = isColor;
};
</script>
