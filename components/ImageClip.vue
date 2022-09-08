<template lang="">
    <div class="grid-holder">
        <!-- <div ref="mouse" id="mouse"></div> -->
        <div class="grid">
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
            <div class="grid-item"></div>
        </div>
    </div>
</template>
<script>
export default {
    name:"ImageClip",
    methods:{
        cursor: function(){
            console.log("clip works")
        }
    },
    created: function(){
        this.cursor()
    }

}
</script>
<style lang="scss">
    #mouse {
        position: absolute;
        width: 64px;
        height: 64px;
        margin: -32px 0px 0px -32px;
        border: 1px solid #000000;
        border-radius: 50%;
        pointer-events: none !important;
        box-shadow: 0 0 16px rgba(255, 255, 255, 0);
    }
    .grid-holder{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        width: 100%;
    }
    .grid{
        display: flex;
        flex-wrap: wrap;
        max-width: 450px;
        gap: 10px;
        .grid-item {
            width: 75px;
            height:75px;
            background-image: url("https://iust-projects.ir/assets/images/projects/dip/8/wiki/image2.bmp");;
          }
    }
   
</style>