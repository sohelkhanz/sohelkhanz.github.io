---
title: 
header:
description: 
permalink: /lazyjs
layout: post
---

```
<script type='text/javascript'>
  var fired = false;
```

```
window.addEventListener("scroll", function(){
    if ((document.documentElement.scrollTop != 0 && fired === false) || (document.body.scrollTop != 0 && fired === false)) {
            (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
            (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
             m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
             })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
          ga('create', 'UA-195317358-1', 'auto');
          ga('send', 'pageview');
        fired = true;
      }
  }, true);
</script>
```

```
<div id="disqus_thread">
  <div id="disqus_empty"></div>
</div>
```
এরপর টার্গেট আর ট্রিগার প্রস্তুত করছি।
```
<script>
function load_disqus( disqus_shortname ) {
  
  var is_disqus_empty = document.getElementById('disqus_empty'),
      disqus_target   = document.getElementById('disqus_thread'),
      disqus_embed    = document.createElement('script'),
      disqus_hook     = (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]);
```

স্ক্রিপটিকে অসমকালীন করার জন্য আর এটা তখনই কাজ করবে যখন ট্রিগার আর টার্গেট চালু হবে।
```  
  if( disqus_target && is_disqus_empty ) {
    disqus_embed.type = 'text/javascript';
    disqus_embed.async = true;
    disqus_embed.src = '//' + disqus_shortname + '.disqus.com/embed.js';
    disqus_hook.appendChild(disqus_embed);
    is_disqus_empty.remove();
  }
}
```
এবার স্ক্রল করলে ডিসকাস যাতে লোড হয় সেই স্ক্রিপটি লিখছি।
```
window.addEventListener('scroll', function(e) {
  var currentScroll = document.scrollingElement.scrollTop;
  var disqus_target = document.getElementById('disqus_thread');

  if( disqus_target && (currentScroll > disqus_target.getBoundingClientRect().top - 150) ) {
    load_disqus('60z');
    console.log('Disqus loaded.');
  }
}, false);
</script> 
```
