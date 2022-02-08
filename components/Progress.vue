<template>
    <div class="w-full bg-purple-100 rounded-full h-2" role="progressbar" :aria-valuenow="percentage" aria-valuemin="0" aria-valuemax="100">
        <transition appear @before-appear="beforeEnter" @after-appear="enter">
            <div class="bg-purple-600 h-2 rounded-full"></div>
        </transition>
    </div>
</template>

<script>
export default {
    name: 'BaseProgress',
    props: {
        percentage: {
            type: [String, Number],
            default: 0,
        }
    },
    methods: {
        beforeEnter (el) {
            el.style.width = 0
        },
        enter (el) {
            el.style.width = `${this.percentage}%`
            el.style.transition = `width 1.4s linear`
        }
    }
}
</script>

<style scoped>
@keyframes progress-indeterminate {
  0% {
    width: 0%;
  }
  100% {
    width: 100%;
  }
}
.progressbar {
  transition: width 0.25s ease;
  animation: progress-indeterminate 1.4s ease;
}
</style>