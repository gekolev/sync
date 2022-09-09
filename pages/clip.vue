<template lang="">
    <div class="center-holder">
        <div class="center">
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <rect width="500px" height="500px"/>
            <image xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="https://i.ibb.co/D5k0J2F/front-Artboard-1.png" width="500px" height="500px" />
          </svg>
          
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <defs>
              <clipPath id="mask">
                <circle id="mask-circle" cx="50%" cy="50%" r="20%" style="fill: #ffffff"/>
              </clipPath>
            </defs>
            <g clip-path="url(#mask)">
              <rect width="500px" height="500px"/>
              <image xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="https://i.ibb.co/wYMW3W6/back-Artboard-1.png" width="500px" height="500px" />
            </g>
          </svg>
        </div>
    </div>
</template>
<script>
export default {
    mounted(){
        
var svgElement = document.querySelector('svg');
var maskedElement = document.querySelector('#mask-circle');
var svgPoint = svgElement.createSVGPoint();

function cursorPoint(e, svg) {
    let delay = 10;
    // svgPoint.x = e.clientX;
    // svgPoint.y = e.clientY;
    svgPoint.x += (e.clientX - svgPoint.x) / delay;
    svgPoint.y += (e.clientY - svgPoint.y) / delay;
    return svgPoint.matrixTransform(svg.getScreenCTM().inverse());
}

function update(svgCoords) {
    maskedElement.setAttribute('cx', svgCoords.x);
    maskedElement.setAttribute('cy', svgCoords.y);
}

window.addEventListener('mousemove', function(e) {
  update(cursorPoint(e, svgElement));
}, false);


}
}
</script>
<style scoped lang="scss">
.center{
    margin-top: 10vh;
    position: absolute;
    left: 0;
    right: 0;
    margin-left: auto;
    margin-right: auto;
    width: 500px;
}
svg {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    display: block;
    width: 500px;
    height: 500px;
  }
  
</style>