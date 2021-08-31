<template>
  <transition appear @before-enter="beforeEnter" @enter="enter" :css="false">
    <div class="crad"></div>
  </transition>
</template>

<script>
// @ is an alias to /src
import gsap from "gsap";

export default {
  name: "Basic",
  components: {},
  methods: {
    beforeEnter(el) {
      el.style.opacity = 0;
      el.style.transform = "scale(0,0)";
    },
    enter(el, done) {
      gsap.to(el, {
        duration: 1,
        opacity: 1,
        scale: 1,
        onComplete: done,
      });
    },
  },
};
</script>

<style lang="scss">
.crad {
  width: 50px;
  height: 50px;
  background: teal;
}
</style>
