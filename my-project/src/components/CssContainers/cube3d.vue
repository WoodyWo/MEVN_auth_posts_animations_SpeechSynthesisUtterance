<template>
<body>  
	<div class="container">
        <div class="cube">
            <div class="side front">front</div>
            <div class="side back">back</div>
            <div class="side right">right</div>
            <div class="side left">left</div>
            <div class="side top">top</div>
            <div class="side bottom">bottom</div>
        </div>
    </div>
</body>
  
</template>

<script>
export default {
 mounted() {
    function lul() {
	var rotateY = 0,
		  rotateX = 0;

	document.onkeydown = function (e) {
			   if (e.keyCode === 37) rotateY -= 4
		else if (e.keyCode === 38) rotateX += 4
		else if (e.keyCode === 39) rotateY += 4
		else if (e.keyCode === 40) rotateX -= 4

		document.querySelector('.cube').style.transform = 
      'rotateY(' + rotateY + 'deg)'+
      'rotateX(' + rotateX + 'deg)';
    }
};
 lul()
  }
}
</script>

<style scoped>
* {
	box-sizing: border-box;
}

body {
	background-image: url(http://subtlepatterns2015.subtlepatterns.netdna-cdn.com/patterns/blackorchid.png);
    overflow: hidden;
    height: 100vh;
     /* Add the blur effect */
  /* filter: blur(8px);
  -webkit-filter: blur(8px); */
  
  
  
  /* Center and scale the image nicely */
  /* background-position: center;
  background-repeat: no-repeat; */
  background-size: cover;
}

.container {
	position: relative;
	margin: 200px auto;
	width: 300px;
	height: 300px;
	perspective: 500px;
}

.cube {
	width: inherit;
	height: inherit;
	transform-style: preserve-3d;
}

.side {
	position: absolute;
	width: inherit;
	height: inherit;
	border: 5px solid #fff;
	font: normal 70px Arial;
	text-align: center;
	line-height: 300px;
	color: #fff;
    /* backface-visibility: hidden;  скрывает задние грани*/
}

.front {
	transform: translateZ(150px);
}

.back {
	transform: rotateY(180deg) translateZ(150px);
}

.right {
	transform: rotateY(90deg) translateZ(150px);
}

.left {
	transform: rotateY(-90deg) translateZ(150px);
}

.top {
	transform: rotateX(90deg) translateZ(150px);
}

.bottom {
	transform: rotateX(-90deg) translateZ(150px);
}
</style>
