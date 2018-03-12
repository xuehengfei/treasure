1.每隔6s触发click事件  setInterval定时6s事件，trigger触发bx-next的click事件
$(function () {setInterval(function () { $('.bx-next').trigger('click') }, 6000) })

2.亿美短信接口
http://mtn.b2m.cn:8080/static/doc/getupstream_or.html

3.视频弹窗插件
mp4格式：
将video播放器放入容器中，关闭时清空容器的内容，不限制多个视频
<script>
	$('.vidbtn').click(function(){
		$('.vidbox').css("visibility","visible");
		var video = $(this).attr('id');//获取视频路径
		$('.vidbox .container').html("<video id='video'  src='"+video+"' preload='auto' controls='controls' autoplay='autoplay'></video>");
	});
	function close1(){
		$('.vidbox .container').html("");
		$('.vidbox').css("visibility","hidden");
	}
</script>
iframe：
参考https://www.supermap.com/events/gtc2017/

如何弹出全屏视频呢

<div class="vdobox">
	<video id="mario-video" controls autoplay="autoplay" style="display: none;">
		<source src="">
	</video>
</div>
<a alt="http://www.guangfan.com/Public/Gf2016/images/video2.mp4" class="iframe">video2</a>
<a alt="http://www.guangfan.com/Public/Gf2016/images/video.mp4" class="iframe">video</a>

<script>
	var aLi = document.querySelectorAll('.iframe');
	var  timer, videoHight = 500;///////////
	for (var i = 0; i < aLi.length; i++) {
		aLi[i].addEventListener('click', function () {
					//开始视频弹出事件
					var marioVideo = document.getElementById("mario-video");
					var hhh = document.getElementById("heool");
					document.getElementById("heool").style.display = "block";
					///////////////////////////
					timer = setInterval(function () {
						if (marioVideo.offsetHeight == videoHight) {
							document.getElementById("marioVideo").style.display = "none";
							clearInterval(timer)
						}
					}, 10)
					///////////////////////////
					if (marioVideo && this) {
						marioVideo.src = this.getAttribute("alt");
						if (marioVideo.requestFullscreen) {
							marioVideo.requestFullscreen();
						}
						else if (marioVideo.msRequestFullscreen) {
							marioVideo.msRequestFullscreen();
						}
						else if (marioVideo.mozRequestFullScreen) {
							marioVideo.mozRequestFullScreen();
						}
						else if (marioVideo.webkitRequestFullScreen) {
							marioVideo.webkitRequestFullScreen();
						}
					}
					//结束
				}
		);
	}
</script>

