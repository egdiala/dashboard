<template>
    <div class="filter-item">
        <span><slot></slot></span>
        <Icon icon="x"></Icon>
    </div>
</template>

<script>
import './filteritem.css';
import Icon from "./Icon.vue";
export default {
    components: { Icon }
}
</script>

<style>
.filter-item div .feather-x {
    width: 20px;
    height: 20px;
}
</style>