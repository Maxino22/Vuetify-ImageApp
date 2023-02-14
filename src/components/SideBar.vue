<template>
  <VNavigationDrawer expand-on-hover rail>
    <v-list>
      <v-list-item
        prepend-avatar="https://res.cloudinary.com/maxino/image/upload/v1666681528/images/20221025/Maxino_uzoiyj.jpg"
        title="Maxwell Muhanda"
        subtitle="ajaybullec@gmail.com"
      ></v-list-item>
    </v-list>

    <VDivider></VDivider>
    <VList density="compact" nav>
      <VListItem
        prepend-icon="mdi-image"
        title="Color Gallery"
        value="Color"
        @click="selectOption(true)"
      />
      <VListItem
        prepend-icon="mdi-dialpad"
        title="GraySpace *"
        value="Color"
        @click="selectOption(false)"
      />
    </VList>
  </VNavigationDrawer>
</template>

<script setup>
const emits = defineEmits(["selectOption"]);

const selectOption = (isColor) => {
  emits("selectOption", isColor);
};
</script>
