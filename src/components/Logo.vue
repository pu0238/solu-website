<template>
    <span class="inline text-4xl font-cal" :class="{
        'text-white': textColor === 'white',
        'text-black': textColor === 'black',
    }">
        Solu
    </span>
</template>

<script lang="ts">
import { reactive } from "vue";

export default {
    name: "Logo",
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
