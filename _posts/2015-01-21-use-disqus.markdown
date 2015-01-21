---
layout: post
title:  "Disqus的接入"
date:   2015-01-21 23:41:08
categories: blog
---

博客的大体框架搭好了，没有评论功能感觉太不专业，果断接入Disqus @。@

####Disqus账号
使用Disqus需要账号，按注册流程走一遍，如果有gmail账号的就直接用gmail登陆也是可以滴。

注册完，接下来会让你输入你准备使用的二级域名，因为我的域名是frend.cc，我就填了frendcc。


####选择博客的搭建平台
选择“Settings” -> “Install”，会出现九个可以选择的平台。

但是。。。。为何没有Jekyll？于是我全部点了一遍，后面选择了“Universal Code”，不要问我为什么，因为他会给你生成一段内嵌的脚本（使用过第三方插件或者服务的应该都懂的其中的原因）

{% highlight javascript %}

<div id="disqus_thread"></div>
<script type="text/javascript">
    /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
    var disqus_shortname = 'frendcc'; // required: replace example with your forum shortname

    /* * * DON'T EDIT BELOW THIS LINE * * */
    (function() {
        var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
        dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>

{% endhighlight %}







