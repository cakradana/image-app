<template>
  <VApp>
    <Sidebar @selectOption="onSelectOption" />
    <VMain>
      <ImageGallery :isWithColor="isWithColor" />
    </VMain>
  </VApp>
</template>

<script setup>
import { ref } from "vue";
import ImageGallery from "./components/ImageGallery.vue";
import Sidebar from "./components/Sidebar.vue";

const isWithColor = ref(true);

const onSelectOption = (isColor) => {
  isWithColor.value = isColor;
};
</script>
