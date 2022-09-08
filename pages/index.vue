<template>
<div>
  <Mouse/>
  <div>
    <h1>Hey, Filip <br> there's two inner pages /clip and /scroll<br> where you can find the tasks from the email! </h1>
    
  </div>
</div>
</template>

<script>
import AnimationTest from '../components/AnimationTest.vue';
import Mouse from '../components/Mouse.vue';
import ImageClip from '../components/ImageClip.vue';
export default {
    name: "IndexPage",
    components: { AnimationTest, Mouse, ImageClip }
}
</script>
<style>
 h1{
  font-family: Verdana, sans-serif;
  font-size: 48px;
  padding: 200px;
 }
</style>