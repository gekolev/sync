<template>
    <div>
        <svg ref="svg"></svg>
    </div>
</template>
<script>
export default {
    name: 'Mouse',
    methods:{
        cursor: function(){
        }
    },
    created: function(){
        this.cursor()
    }
}

</script>
<style lang="scss">
    body {
        overflow: hidden;
      }
      svg {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
      }
      line {
        stroke: #263cb9;
        stroke-width: 3;
      }
</style>