<template>
<header class="navbar" v-bind="$attrs">
  <div class="flex flex-grow items-center">
    <slot></slot>
  </div>
</header>
</template>

<script>
import './navbar.css';
/**
 * A simple Navbar component for navigation. To avoid issues on the frontend, the Navbar should be placed within the Main component.
**/

export default {
    name: 'BaseNavbar',

}
</script>