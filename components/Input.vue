<template>
    <div class="p-0 border-0 shadow-none text-left">
        <label v-if="label" class="nova-label">{{ label }}</label>
        <div class="mt-1 relative block">
            <span v-if="icon" :class="`absolute inset-y-0 flex items-center ${iconRight}`">
                <Icon v-if="iconPosition == 'left'" :icon="icon" class="fill-slate-300 text-gray-400" />
            </span>
            <input class="input" v-bind="$attrs" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)"/>
            <slot></slot>
            <span v-if="icon" :class="`absolute inset-y-0 flex items-center ${iconRight}`">
                <Icon v-if="iconPosition == 'right'" :icon="icon" class="fill-slate-300 text-gray-400" />
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
}
</script>