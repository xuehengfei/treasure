1.每隔6s触发click事件  setInterval定时6s事件，trigger触发bx-next的click事件
$(function () {setInterval(function () { $('.bx-next').trigger('click') }, 6000) })

2.亿美短信接口
http://mtn.b2m.cn:8080/static/doc/getupstream_or.html

2.视频弹窗插件
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
