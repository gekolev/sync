<template>
    <div>
        <transition
        appear
        @before-enter="beforeEnter"
        @enter="enter"
        :css="false"
        >
            <h1 v-if="showTitle">Hello world</h1>
        </transition>
    </div>
</template>
<script>
//testing if gsap and vue work
import { ref } from 'vue';
import gsap from 'gsap';

export default {

    setup() {
    const showTitle = ref(true)
    const beforeEnter = (el) => {
    //   console.log('before enter - set intial state')
      el.style.transform = 'translateY(-60px)'
      el.style.opacity = 0
    }
    const enter = (el, done) => {
    //   console.log('starting to enter - make transition')
      gsap.to(el, {
        duration: 4,
        y: 0,
        opacity: 1,
        ease: 'bounce.out',
        onComplete: done
      })
    }
    return { beforeEnter, enter, showTitle }
  }
    
}
</script>
<style lang="scss">

</style>