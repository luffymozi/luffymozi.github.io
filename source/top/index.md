---
title: 热度排行榜
comments: false
keywords: top,文章阅读量排行榜
description: 博客文章阅读量排行榜
---
<div id="top"></div>

<script src="//cdn1.lncld.net/static/js/3.0.4/av-min.js"></script>
<script>AV.initialize("ma06vxLXgDolN9osc5zQFLWz-gzGzoHsz", "EmR2dGVC6k7D2vBs432FpKCf");</script>
<script type="text/javascript">
    var time=0
    var title=""
    var url=""
    var query = new AV.Query('Counter');
    query.notEqualTo('id',0);
    query.descending('time');
    query.limit(1000);
    query.find().then(function (todo) {
        for (var i=0;i<1000;i++){
            var result=todo[i].attributes;
            time=result.time;
            title=result.title;
            url=result.url;
            var content="<a href='"+"http://sunny.chat"+url+"'>"+title+"</a>"+"<br />"+"<font color='#555'>"+"【文章热度:"+time+"℃】"+"</font>"+"<br /><br />";
            document.getElementById("top").innerHTML+=content
        }
    }, function (error) {
        console.log("error");
    });
</script>

<style>.post-description { display: none; }</style>