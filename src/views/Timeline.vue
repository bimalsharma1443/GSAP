<template>
  <div>
    <img class="runner first" src="../assets/logo.png" alt="runner" />
    <img class="runner second" src="../assets/logo.png" alt="runner" />
    <img class="runner third" src="../assets/logo.png" alt="runner" />
  </div>
</template>

<script>
import gsap from 'gsap'

export default {
  mounted() {
    let tl = gsap.timeline({ repeat: -1, repeatDelay: 1 })
    tl.to('.first', { x: 700, duration: 2, ease: 'expo.out' })
    // tl.to('.second', { x: 700, duration: 2, ease: 'expo.out' }, 0.5) //now with an absolute position
    // tl.to('.third', { x: 700, duration: 2, ease: 'expo.out' }, '-=1')
    // tl.to('.second', { x: 700, duration: 2, ease: 'expo.out' }, '<') // starts when first tween starts
    // tl.to('.third', { x: 700, duration: 2, ease: 'expo.out' },  '<') // starts when second tween starts, which is when first tween starts
    tl.to('.second', { x: 700, duration: 2, ease: 'expo.out' }, '<0.5') // What will this do?
    tl.to('.third', { x: 700, duration: 2, ease: 'expo.out' })
  }
}
</script>

<style scoped>
.runner {
  display: block;
  height: 5em;
  width: 5em;
  margin-top: 1.5em;
}
</style>
