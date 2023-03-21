<template>
  <nav>
    <ul >
      <NavItem v-for="item, index in navItems"
        :isComingSoon="item.isComingSoon"
        :content="item.content"
        textColor="black"
        :decoration="index === navItems.length - 1"
      />
    </ul>
  </nav>
</template>

<script lang="ts">
import { PropType, reactive } from "vue";
import NavItem from "./NavItem.vue";

export default {
  components: { NavItem },
  name: "NavBar",
  props: {
    navItems: {
      type: Array as PropType<{ isComingSoon: boolean; content: string }[]>,
      default: () => [
        { isComingSoon: false, content: "services" },
        { isComingSoon: false, content: "process" },
        { isComingSoon: false, content: "technologies" },
        { isComingSoon: false, content: "about us" },
        { isComingSoon: true, content: "case studies" },
        { isComingSoon: false, content: "contact" },
      ],
      required: true,
      validator: (color: string) => ["white", "black"].includes(color),
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
