<template>
    <div class="flex space-x-2 items-center">
        <input class="checkbox" v-bind="$attrs" type="checkbox" :checked="modelValue" @change="$emit('update:modelValue', $event.target.checked)" />
        <label v-if="label" class="label">
            {{ label }}
        </label>
        <slot></slot>
    </div>
</template>

<script>
import './checkbox.css';

export default {
    name: 'BaseCheckbox',
    props: {
        label: {
            type: String,
            default: ''
        },
        modelValue: {
            type: Boolean,
            default: false
        }
    }
}
</script>