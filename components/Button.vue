<template>
  <button v-if="!to" v-bind="$attrs" type="button" :class="classes">
    <Icon v-if="icon && iconPosition == 'left'" :icon="icon" width="20" height="20"></Icon>
    <slot></slot>
        <span v-if="label">{{ label }}</span>
    <Icon v-if="icon && iconPosition == 'right'" :icon="icon" width="20" height="20"></Icon>
    </button>
  <nuxt-link v-else :to="to" v-bind="$attrs" type="button" :class="classes">
    <span v-if="label">{{ label }}</span>
  </nuxt-link>
</template>

<script >
import './button.css';
import Icon from './Icon.vue';

export default {
    name: "BaseButton",
    components: { Icon },
    props: {
        label: {
            type: String,
            default: ""
        },
        icon: {
            type: String,
            default: ''
        },
        iconPosition: {
            type: String,
            default: 'left'
        },
        to: {
            type: String,
            default: ""
        },
        regular: {
            type: Boolean,
        },
        text: {
            type: Boolean,
        },
        iconbutton: {
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
                "button": true,
                "button--regular": this.regular,
                "button--text": this.text,
                "button--outlined": this.outlined,
                "button--icon": this.iconbutton
            };
        }
    }
}
</script>