<template>
    <Icon :icon="icon" v-bind="$attrs" />
</template>

<script >
import './icon.css';
import { Icon } from '@iconify/vue2/dist/offline.mjs';

export default {
    name: 'BaseIcon',
    components: { Icon },
    props: {
        icon: {
            type: String,
            required: true
        }
    },
    emits: ["click"],
}
</script>