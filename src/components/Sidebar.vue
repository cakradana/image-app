<template>
  <VNavigationDrawer expand-on-hover rail>
    <VList>
      <VListItem
        prepend-avatar="https://avatars.githubusercontent.com/u/54362263?v=4"
        title="R. Cakradana"
        subtitle="rcakradana@gmailcom"
      >
      </VListItem>
    </VList>
    <VDivider></VDivider>
    <VList density="compact" nav>
      <VListItem
        prepend-icon="mdi-palette"
        title="Color Gallery"
        value="color"
        @click="selectOption(true)"
      />
      <VListItem
        prepend-icon="mdi-image"
        title="Grayscale Gallery"
        value="grayscale"
        @click="selectOption(false)"
      />
    </VList>
  </VNavigationDrawer>
</template>

<script setup>
import { defineEmits } from "vue";

const emits = defineEmits(["selectOption"]);

const selectOption = (isColor) => {
  emits("selectOption", isColor);
};
</script>
