<template>
    <div>
        <svg></svg>
    </div>
</template>
<script>
import { gsap } from 'gsap';
export default {
    
mounted() {    
let svgns = "http://www.w3.org/2000/svg";
let root = document.querySelector("svg");
let ease = 0.75;

let pointer = { 
  x: window.innerWidth  / 2, 
  y: window.innerHeight / 2 
};

window.addEventListener("mousemove", (event) => {
  pointer.x = event.clientX;
  pointer.y = event.clientY;
});

let leader = (prop) => {
  return prop === "x" ? pointer.x : pointer.y;
}

let total = 200;
for (let i = 0; i < total; i++) {
  leader = createLine(leader, i);
}

function createLine(leader, i) {
  
  let line = document.createElementNS(svgns, "line");
  root.appendChild(line);
  
  gsap.set(line, { x: -1500, y: -750 });
  
  let pos = gsap.getProperty(line);
    
  gsap.to(line, {
    duration: 10000,
    x: "+=150",
    y: "+=10",
    repeat: -1,
    ease: "expo.inOut",
    modifiers: {
      x: () => {        
        let posX = pos("x");
        let leaderX = leader("x");
        let x = posX + (leaderX - posX) * ease;
        line.setAttribute("x2", leaderX - x);
        return x;
      },
      y: () => {        
        let posY = pos("y");
        let leaderY = leader("y");
        let y = posY + (leaderY - posY) * ease;
        line.setAttribute("y2", leaderY - y);
        return y;
      }
    }
  });  
  
  return pos;
}
}

};

</script>
<style lang="scss">
      svg {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
        z-index: -1;
      }
      line {
        stroke: #263cb9;
        stroke-width: 3;
      }
</style>