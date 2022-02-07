<template>
  <div>
    <Button label="hellos" regular></Button>
    <Icon icon="bell"></Icon>
  </div>
</template>

<script>
import Button from "../components/Button.vue";
import Icon from "../components/Icon.vue";
export default {
    name: "IndexPage",
    components: { Button, Icon }
}
</script>
