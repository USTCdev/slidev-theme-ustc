<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "../layoutHelper";
import bg1 from "../assets/backgrounds/bg1.jpg";
import bg2 from "../assets/backgrounds/bg2.jpg";
import bg3 from "../assets/backgrounds/bg3.jpg";
import bg4 from "../assets/backgrounds/bg4.jpg";

const props = defineProps({
  background: {
    type: [Number, String],
    default: 1,
  },
});

const style = computed(() => {
  if (typeof props.background === "number") {
    return handleBackground([bg1, bg2, bg3, bg4][props.background], true);
  } else {
    return handleBackground(props.background, true);
  }
});
</script>

<template>
  <div class="slidev-layout cover text-center" :style="style">
    <div class="my-auto w-full">
      <slot />
    </div>
  </div>
</template>
