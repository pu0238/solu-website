<template>
  <button
    class="px-4 py-2 font-semibold border-4 border-purple-700 font-josefin disabled:text-neutral-200"
    :class="{
      'bg-purple-700 text-white disabled:bg-purple-900 disabled:border-purple-900':
        isFilled,
      'bg-transparent  text-purple-700 disabled:text-purple-900 disabled:border-purple-900':
        !isFilled,
    }"
    type="button"
    :disabled="isDisabled"
  >
    {{ content }}
  </button>
</template>

<script lang="ts">
import { reactive } from "vue";

export default {
  name: "button",
  props: {
    isDisabled: {
      type: Boolean,
      default: false,
      required: true,
    },
    isFilled: {
      type: Boolean,
      default: true,
      required: true,
    },
    content: {
      type: String,
      default: "Click me!",
      required: true,
    },
  },
  setup(props) {
    props = reactive(props);
    return {};
  },
};
</script>
