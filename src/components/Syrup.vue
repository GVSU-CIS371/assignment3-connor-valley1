<template>
  <div class="syrup vanilla" :style="syrupStyle"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";
import { syrups, currentSyrup } from "../stores/beverage";

const syrupStyle = computed(() => {
  const selectedSyrup = syrups.value.find((s) => s.id === currentSyrup.value);
  const color = selectedSyrup!.color;

  return {
    background: `repeating-linear-gradient(45deg, white, white 10px, ${color} 10px, ${color} 20px)`
  };
});

</script>

<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
