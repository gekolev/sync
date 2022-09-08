<template lang="">
    <div>
        <div class="center">
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink= "http://www.w3.org/1999/xlink">
            <rect width="50%" height="50%" fill="#E7E7E8"/>
            <image xmlns:xlink= "http://www.w3.org/1999/xlink" xlink:href="https://cdn11.bigcommerce.com/s-3uewkq06zr/products/315/images/514/bs_red__30528.1492536976.500.750.png?c=2" width="50%" height="50%" />
          </svg>
          
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <defs>
              <clipPath id="mask">
                <circle id="mask-circle" cx="50%" cy="50%" r="8%" style="fill: #ffffff"/>
              </clipPath>
            </defs>
            <g clip-path="url(#mask)">
              <rect width="50%" height="50%" fill="#272730"/>
              <image xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="https://images.squarespace-cdn.com/content/v1/5aa038113917eedcf3312352/1527780672674-HH4WEVTYQM6GT41VT7QF/green.png?format=2500w" width="50%" height="50%" />
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
    svgPoint.x = e.clientX;
    svgPoint.y = e.clientY;
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
    display: flex;
    align-items: center;
    justify-content: center;
}
svg {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    display: block;
    width: 100%;
    height: 100%;
  }
</style>