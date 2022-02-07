<template>
    <div v-bind="$attrs" v-html="$feathericons[icon].toSvg()"></div>
</template>

<script >
import './icon.css';

export default {
    name: 'BaseIcon',
    props: {
        icon: {
            type: String,
            required: true
        }
    }
}
</script>