<template>
  <button class="bg-purple-700" type="button" :disabled="isDisabled">{{ content }}</button>
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

    content: {
      type: String,
      default: "Click me!",
      required: true,
    },
    backgroundColorClass: {
      type: String,
      default: "bg-purple-700",
    },
  },
  setup(props) {
    props = reactive(props);
    return {};
  },
};
</script>
