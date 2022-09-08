<template>
<div>
  <!-- <Mouse/> -->
  <client-only>
    <Clip/>
  </client-only>
</div>
</template>

<script>
import AnimationTest from '../components/AnimationTest.vue';
import Mouse from '../components/Mouse.vue';
import Clip from '../components/Clip.vue';
export default {
    name: "IndexPage",
    components: { AnimationTest, Mouse, Clip }
}
</script>
<style >

</style>