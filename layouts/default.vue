<template>
    <div>
        <Navbar></Navbar>
        <Nuxt/>
    </div>
</template>
 
<script>
import Navbar from "../components/Navbar.vue";
export default {
    name: 'DefaultLayout',
    components: { Navbar }
}
</script>