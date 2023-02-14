<template>
  <VCard class="mx-5 my-2 pa-3">
    <VRow>
      <VCol cols="4" sm="3" md="2" lg="1" v-for="n in 200" :key="n">
        <VHover v-slot="{ isHovering, props }">
          <VCard
            :elevation="isHovering ? 12 : 2"
            v-bind="props"
            @click="
              copyURL(
                `https://picsum.photos/500/300?image=${n * 5 + 10}${
                  p.isWithColor ? '' : '&grayscale'
                }`
              )
            "
          >
            <VImg
              aspect-ratio="1"
              cover
              :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${
                p.isWithColor ? '' : '&grayscale'
              }`"
              :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${
                p.isWithColor ? '' : '&grayscale'
              }`"
            >
              <template v-slot:placeholder>
                <VRow align="center" class="fill-height ma-0" justify="center">
                  <v-progress-circular
                    color="grey-lighten-4"
                    indeterminate
                  ></v-progress-circular>
                </VRow>
              </template>
            </VImg>
          </VCard>
        </VHover>
      </VCol>
    </VRow>
  </VCard>
</template>

<script setup>
const p = defineProps({
  isWithColor: {
    type: Boolean,
    required: true,
  },
});

async function copyURL(url) {
  await navigator.clipboard.writeText(url);
}
</script>
