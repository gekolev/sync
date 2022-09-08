<template lang="">
    <div class="image-holder">
        <img v-bind:src="image.title"/>
    </div>
</template>
<script>
export default {
    props: ["image"],
}
</script>
<style lang="scss">
.image-holder{
    img{
        max-width: 600px;
    }
    margin-top: 50px;
    margin-bottom: 50px;
    &:first-child{
        margin-top:0px;
    }
}
</style>
