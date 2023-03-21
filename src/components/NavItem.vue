<template>
  <li
    class="relative inline float-left py-2 mx-2 font-semibold font-josefin"
    :class="{
      'text-white': textColor === 'white',
      'text-black': textColor === 'black',
      'text-neutral-400': isComingSoon,
      'bg-purple-700 text-white -mt-24 pt-24 bottom-0 px-4': decoration,
      'px-1': !decoration,
    }"
  >
    {{ content }}
    <span
      v-if="isComingSoon"
      class="absolute bottom-0 -ml-4 text-xs text-neutral-400"
    >
      soon!</span
    >
  </li>
</template>

<script lang="ts">
import { reactive } from "vue";

export default {
  name: "NavItem",
  props: {
    decoration: {
      type: Boolean,
      default: false,
    },
    isComingSoon: {
      type: Boolean,
      default: false,
    },
    content: {
      type: String,
      default: "Menu item!",
      required: true,
    },
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
