<template>
    <div v-if="show" class="filter-item">
        <span><slot></slot></span>
        <button type="button" class="bg-transparent cursor-pointer border-none text-purple-700 text-xs chip-close" @click="show = false">
            <Icon icon="x"></Icon>
        </button>
    </div>
</template>

<script>
import './filteritem.css';
import Icon from "./Icon.vue";
export default {
    components: { Icon },
    data() {
        return {
            show: true,
        }
    },
}
</script>

<style>
.filter-item button div .feather-x {
    width: 20px;
    height: 20px;
}
</style>