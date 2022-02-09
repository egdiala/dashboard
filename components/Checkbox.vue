<template>
    <label v-if="!intermediate" class="flex space-x-2 items-center">
        <div :class="`${divClass} border rounded-md  w-5 h-5 flex flex-shrink-0 justify-center items-center`">
            <input ref="input" class="checkbox opacity-0 absolute" v-bind="$attrs" type="checkbox" :checked="modelValue || checked" @change="$emit('update:modelValue', $event.target.checked)" />
            <svg class="fill-current hidden w-3 h-3 bg-purple-50 text-purple-500 pointer-events-none" viewBox="0 0 20 20"><path d="M0 11l2-2 5 5L18 3l2 2L7 18z"/></svg>
        </div>
        <div v-if="label" class="label select-none">
            {{ label }}
        </div>
        <slot></slot>
    </label>
    <label v-else class="flex space-x-2 items-center">
        <div :class="`${divClass} border rounded-md  w-5 h-5 flex flex-shrink-0 justify-center items-center`">
            <input ref="input" class="checkbox opacity-0 absolute" v-bind="$attrs" type="checkbox" :indeterminate.prop="reactiveIntermediate" :checked="intermediate || checked" @change="$emit('update:modelValue', $event.target.checked)" />
            <svg class="fill-current block w-3 h-3 bg-purple-50 text-purple-500 pointer-events-none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="3" fill="none" stroke-linecap="round" stroke-linejoin="round"><line x1="5" y1="12" x2="19" y2="12"></line></svg>
        </div>
        <div v-if="label" class="label select-none">
            {{ label }}
        </div>
        <slot></slot>
    </label>
        <!-- <div class="flex items-center space-x-2">
            <input id="A3-yes" type="checkbox"  v-bind="$attrs" name="A3-confirmation" value="yes" class="checkbox opacity-0 absolute h-5 w-5" :checked="modelValue" @change="$emit('update:modelValue', $event.target.checked)" />
            <div class="bg-white focus:bg-purple-200 border rounded-md border-gray-300 w-5 h-5 flex flex-shrink-0 justify-center items-center focus:ring-purple-200">
                <svg class="fill-current hidden w-3 h-3 text-purple-700 pointer-events-none" version="1.1" viewBox="0 0 17 12" xmlns="http://www.w3.org/2000/svg">
                    <g fill="none" fill-rule="evenodd">
                        <g transform="translate(-9 -11)" fill="#9333ea" fill-rule="nonzero">
                            <path d="m25.576 11.414c0.56558 0.55188 0.56558 1.4439 0 1.9961l-9.404 9.176c-0.28213 0.27529-0.65247 0.41385-1.0228 0.41385-0.37034 0-0.74068-0.13855-1.0228-0.41385l-4.7019-4.588c-0.56584-0.55188-0.56584-1.4442 0-1.9961 0.56558-0.55214 1.4798-0.55214 2.0456 0l3.679 3.5899 8.3812-8.1779c0.56558-0.55214 1.4798-0.55214 2.0456 0z" />
                        </g>
                    </g>
                </svg>
            </div>
            <label v-if="label" for="A3-yes" class="label select-none">Yes</label>
        </div> -->
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
        },
        checked: {
            type: Boolean,
            default: false
        },
        intermediate: {
            type: Boolean,
            default: false
        }
    },
    data() {
        return {
            reactiveIntermediate: false,
            divClass: ''
        }
    },
    mounted() {
        this.checkedClass();
        if (this.intermediate === true) {
            this.reactiveIntermediate = true
        } else {
            this.reactiveIntermediate = false
        }
    },
    methods: {
        checkedClass() {
            // eslint-disable-next-line eqeqeq
            if (this.$refs.input.checked == true) {
                this.divClass = 'bg-purple-50 border-purple-500';
            } else {
                this.divClass = 'bg-white border-gray-300';
            }
        }
    },
}
</script>