<template>
  <VCard class="ma-3 pa-6">
    <VRow>
      <VCol v-for="n in 100" cols="4" sm="3" md="2" lg="1">
        <VHover v-slot="{ isHovering, props }">
          <VCard
            :elevation="isHovering ? 12 : 2"
            v-bind="props"
            @click="
              copyUrl(
                `https://picsum.photos/500/300?image=${n * 5 + 10}${
                  query.isWithColor ? `` : `&grayscale`
                }`
              )
            "
          >
            <VImg
              :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${
                query.isWithColor ? `` : `&grayscale`
              }`"
              :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${
                query.isWithColor ? `` : `&grayscale`
              }`"
              aspect-ratio="1"
              cover
            >
              <template v-slot:placeholder>
                <VRow class="fill-height ma-0" align="center" justify="center">
                  <VProgressCircular indeterminate color="grey-lighten-5">
                  </VProgressCircular>
                </VRow>
              </template> </VImg
          ></VCard>
        </VHover>
      </VCol>
    </VRow>
  </VCard>
</template>

<script setup>
import { defineProps } from "vue";

const query = defineProps(["isWithColor"]);

const copyUrl = async (url) => {
  await navigator.clipboard.writeText(url);
};
</script>
