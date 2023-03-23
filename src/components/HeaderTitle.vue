<template>
  <h1 class="text-6xl font-cal"
        :class="{
          'text-black': textColor === 'white',
          'text-white': textColor === 'black',
        }"
  >
    <span
      class="relative"
      :class="{
        'text-white text-stroke-black-3': textColor === 'white',
        'text-black text-stroke-white-3': textColor === 'black',
      }"
      >Comprehensive software</span
    >
    for the 21st century!
  </h1>
</template>

<script lang="ts">
import { reactive } from "vue";

export default {
  name: "NavItem",
  props: {
    textColor: {
      type: String,
      default: "black",
      required: true,
      validator: (color: string) => ["white", "black"].includes(color),
    },
  },
  setup(props) {
    props = reactive(props);
    return {};
  },
};
</script>
