<template>
  <button v-if="!to" v-bind="$attrs" type="button" :class="classes">
    <span v-if="label">{{ label }}</span>
  </button>
  <!-- <nuxt-link v-if="to && !isExternalLink" :to="to" v-bind="$attrs" type="button" :class="classes" @click="onClick" :style="style">
    <Icon v-if="icon && iconPosition == 'left' ||  iconPosition == ''" :icon="icon" />
    <span v-if="label">{{ label }}</span>
    <Icon v-if="icon && iconPosition == 'right'" :icon="icon" />
  </nuxt-link> -->
</template>

<script >
import './button.css';
// import Icon from './Icon.vue';

export default {
    name: "BaseButton",
    // components: { Icon },
    props: {
        label: {
            type: String,
            default: ''
        },
        to: {
            type: String,
            default: ''
        },
        regular: {
            type: Boolean,
        },
        text: {
            type: Boolean,
        },
        outlined: {
            type: Boolean,
        }
    },
    emits: ["click"],
    computed: {
        classes() {
            return {
                'button': true,
                'button--regular': this.regular,
                'button--text': this.text,
                'button--outlined': this.outlined
            }
        }
    },
}
</script>