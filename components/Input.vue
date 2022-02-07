<template>
    <div class="p-0 border-0 shadow-none text-left w-full">
        <div class="relative block">
            <span v-if="icon" :class="`absolute inset-y-0 flex items-center ${position}`">
                <Icon v-if="icon && iconPosition == '' || iconPosition == 'left'" :icon="icon" class="fill-slate-300 text-gray-400" />
            </span>
            <input :class="`input ${inputPadding}`" type="text" v-bind="$attrs" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)"/>
            <slot></slot>
            <span v-if="icon" :class="`absolute inset-y-0 flex items-center ${position}`">
                <Icon v-if="icon && iconPosition == '' || iconPosition == 'right'" :icon="icon" class="fill-slate-300 text-gray-400" />
            </span>
        </div>
    </div>
</template>

<script >
import Icon from './Icon.vue';
import './input.css';

export default {
    name: 'BaseInput',
    components: { Icon },
    props: {
        icon: {
            type: String,
            default: ''
        },
        iconPosition: {
            type: String,
            default: ''
        },
        modelValue: {
            type: [String, Number],
            default: ''
        }
    },
    computed: {
        position() {
            if (this.icon) {
                return this.iconPosition === 'right' ? 'right-0 pr-3.5' : 'left-0 pl-3.5';
            } else {
                return '';
            }
        },
        inputPadding() {
            if (this.icon) {
                return this.iconPosition === 'right' ? 'pr-11' : 'pl-11';
            } else {
                return '';
            }
        },
    },
}
</script>