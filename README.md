<!DOCTYPE html>
<html>
<body style="background:black; color:white; font-size:40px; text-align:center;">
  <canvas id="c"></canvas>
  <div id="msg">🎆 新年快乐！愿你新的一年心想事成！</div>

<script>
const c = document.getElementById("c");
const ctx = c.getContext("2d");
c.width = window.innerWidth;
c.height = window.innerHeight;
const fireworks = [];

function boom(x, y){
  for(let i=0;i<80;i++){
    fireworks.push({
      x, y,
      vx: (Math.random()*2-1)*4,
      vy: (Math.random()*2-1)*4,
      life: 60
    });
  }
}

setInterval(()=>boom(Math.random()*c.width, Math.random()*c.height/2), 800);

function animate(){
  ctx.fillStyle="rgba(0,0,0,0.2)";
  ctx.fillRect(0,0,c.width,c.height);
  fireworks.forEach(f=>{
    ctx.fillStyle="hsl("+(Math.random()*360)+",100%,60%)";
    ctx.fillRect(f.x, f.y, 3, 3);
    f.x+=f.vx; f.y+=f.vy; f.life--;
  });
  for(let i=fireworks.length-1;i>=0;i--)
    if(fireworks[i].life<=0) fireworks.splice(i,1);
  requestAnimationFrame(animate);
}
animate();
</script>
</body>
</html>
