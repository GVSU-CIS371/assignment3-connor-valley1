<template>
  <div class="baseBeverage" :style="{ backgroundColor: baseColor}"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";
import { bases, currentBase } from "../stores/beverage";

const baseColor = computed(() => {
  const selectedBase =  bases.value.find((b) => b.id === currentBase.value);
  return selectedBase!.color;
});

</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
</style>
