<!DOCTYPE html>
<html>
<head>
<title>Autoplay Prototype</title>
<link rel="stylesheet" href="index.css">
<link href="http://vjs.zencdn.net/5.19/video-js.min.css" rel="stylesheet">
<script src="http://vjs.zencdn.net/5.19/video.min.js"></script>
<script src="http://vjs.zencdn.net/ie8/1.1.2/videojs-ie8.min.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

<script>
$(document).ready(function(){
	console.log($);
	console.log('jquery');
		var player2 = videojs("video2");
	$('#playbutton').on('click', function(){
				player2.currentTime(5);
			player2.play();
	});
	$('#pausebutton').on('click', function(){
			player2.pause();
				console.log("current  time is " + player2.currentTime());
	});

});

$(document).ready(function(){
		$("#removeAutoPlayButton").click(function(){

				$("#video1").removeAttr("autoplay");
		});
		$("#addAutoplayButton").click(function(){
				$("#video2").attr("autoplay","");
		});
});

$(document).ready(function(){
		$(`#parentDiv video`).click(function(){
				console.log("click on the videw");
				
		});
		$(`#parentDiv`).click(function(){
				console.log("click on the parent div");
				
		});
});

</script>
<style>
h1 {
	color: red;
}
ol {
	position: relative;
	top: 300px;
	width: 4000px;
	bottom: 50px;
}

li {
	position: inline;
	float: left;
	margin-right: 700px;
}

</style>
</head>
<body>


<h1 id="title">Autoplay Prototype</h1>
<div id = "parentDiv">
	<ol>
		<li>
			<video id="video1"
				playsinline
				muted = "true"
				controls
    			class="video-js"
    			preload="auto"
  				src="http://vjs.zencdn.net/v/oceans.mp4">
			</video>
		</li>
		<li>
			<button id="removeAutoPlayButton">removeAutoplay</button>
			<button id = "addAutoplayButton">addAutoplay</button>
			<button id="playbutton">play</button>
			<button id="pausebutton">pause</button>
			<video id="video2"
				playsinline
				muted = "true"
    			class="video-js"
    			preload="auto"
  				src="http://vjs.zencdn.net/v/oceans.mp4">
			</video>
		</li>
	</ol>
</div>

</body>
</html>
