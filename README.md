# <!DOCTYPE html>
<html>
<head>
<title>Valentine 💘</title>

<style>
body{
margin:0;
background:black;
color:white;
font-family:Arial;
text-align:center;
overflow:hidden;
}

#glow{
position:fixed;
inset:0;
box-shadow:0 0 40px red inset;
display:none;
}

#main{
display:none;
margin-top:100px;
}

h1{color:pink;}

.heart{
position:fixed;
font-size:20px;
animation:float 6s linear infinite;
}

@keyframes float{
from{transform:translateY(0);}
to{transform:translateY(-100vh);}
}

.confetti{
position:fixed;
top:0;
width:10px;
height:10px;
background:white;
animation:fall 5s linear infinite;
}

@keyframes fall{
to{transform:translateY(100vh);}
}

#love{
display:none;
font-size:60px;
font-weight:bold;
color:red;
}
</style>
</head>

<body>

<div id="glow"></div>

<div id="main">
<h1>💘 HAPPY VALENTINE'S DAY 💘</h1>
<p>Lifetime subscription activated 😌</p>
</div>

<div id="love">I LOVE YOU ❤️</div>

<script>
window.onload=function(){
alert("🚨 You have been chosen as my Valentine 🚨");
document.getElementById("glow").style.display="block";
}

setTimeout(()=>{
document.getElementById("main").style.display="block";
confetti();
setInterval(heart,400);
},3000);

setTimeout(()=>{
for(let i=0;i<200;i++)heart();
document.getElementById("love").style.display="block";
},30000);

function heart(){
let h=document.createElement("div");
h.className="heart";
h.innerHTML="❤️";
h.style.left=Math.random()*100+"vw";
h.style.bottom="-20px";
document.body.appendChild(h);
setTimeout(()=>h.remove(),6000);
}

function confetti(){
for(let i=0;i<40;i++){
let c=document.createElement("div");
c.className="confetti";
c.style.left=Math.random()*100+"vw";
c.style.background="hsl("+Math.random()*360+",100%,50%)";
document.body.appendChild(c);
setTimeout(()=>c.remove(),5000);
}
}
</script>

</body>
</html>
