<template>
<div>
  <Mouse/>
  <div class="msg">
    <h1>Hey, Filip <br> there's two inner pages /clip and /scroll<br> where you can find the tasks from the email!</h1>
    <p>Hope to hear from you soon!</p>
  </div>
</div>
</template>

<script>
import Mouse from '../components/Mouse.vue';
export default {
    name: "IndexPage",
    components: { Mouse }
}
</script>
<style>
.msg{
  padding: 200px;
}
 h1{
  font-family: Verdana, sans-serif;
  font-size: 48px;
 }
 p{
  font-size: 24px;
  font-family: Verdana, sans-serif;
 }
</style>