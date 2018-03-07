1.每隔6s触发click事件  setInterval定时6s事件，trigger触发bx-next的click事件
$(function () {setInterval(function () { $('.bx-next').trigger('click') }, 6000) })

2.亿美短信接口
http://mtn.b2m.cn:8080/static/doc/getupstream_or.html
