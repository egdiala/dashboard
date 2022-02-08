<template>
  <div class="flex items-center space-x-1 font-medium pl-2.5 pr-2 py-0.5 rounded-2xl bg-purple-50 ">
    <span class="text-sm text-purple-700"><slot></slot></span>
    <button type="button" class="bg-transparent cursor-pointer border-none text-purple-400 text-xs chip-close">
        <Icon icon="x"></Icon>
    </button>
  </div>
</template>

<script>
import Icon from "./Icon.vue";
export default {
    name: "BaseChip",
    components: { Icon }
}
</script>

<style>
button.chip-close div .feather-x {
    width: 12px;
    height: 12px;
}
</style>