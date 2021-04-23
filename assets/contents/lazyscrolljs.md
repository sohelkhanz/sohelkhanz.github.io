---
title: জাভা ল্যাজি স্ক্রল
header: কিভাবে গুগল এনালাইটিক ও ডিসকাস কমেন্টকে ল্যাজি বা অলস করবেন
description: ওয়েবসাইটকে মার্কেটিং করার জন্য এনালাইটিক ব্যবহার করা হয়। আপনার সাইটে রিয়েলটাইম ভিউয়ারস কত, ইউজাররা কোন দেশ থেকে, কোন আইপি এড্রেস বা কোন ডিভাইস ব্যবহার করছে, আপনার পেজগুলোর যাবতীয় ইনসাইট এনলাইটিকে দেখতে পারবেন। আবার ডিসকাস কমেন্ট অন থাকলে আপনার পেজে যে কেউ কমেন্টস, লাইক, রিয়্যাক্ট করতে পারবে।
permalink: /lazyjs
layout: post
---
তবে বড় সমস্যা এগুলির ডিফল্ট জাভা স্ক্রিপ্ট, ফন্টস আপনার পেজের গতি আর পারফরম্যান্স এর বারোটা বাজিয়ে দিবে। পাশাপাশি আপনার সাইটটির সাইজও বড় হয়ে যাবে। সেক্ষেত্রে আপনি নিজের মত করে স্ক্রিপ্ট কে সেট করতে পারেন যাতে এগুলি অসমকালীনভাবে লোড নেয়। অসমকালীন মানে আপনার পেজ লোড হলে একই সময়ে স্ক্রিপটি লোড নিবে না, কিছুক্ষন পরে লোড নিবে। এক কথায় স্ক্রিপ্টকে অলস করতে হবে। আমি আপনাদের দেখাবে কিভাবে স্ক্রিপ্ট অলস করবেন এবং কিভাবে স্ক্রল করে এর আলসেমিকে কেমনে একটিভ করবেন।
## গুগল এনালাইটিক
এনালাইটিকের ডিফল্ট স্ক্রিপ কপি করে এর ভেতরে এটাকে ফায়ার ভেরিবল এড করে ফল্স দিন।
```
<script type='text/javascript'>
  var fired = false;
```
স্ক্রল ফাংশন ব্যবহার করে পরে এনাইলাইকের কোডটা যোগ করুন। অবশ্যই ট্রাকিং আইডি আপনারটা দিবেন। কোডটা পরলেই বুঝবেন স্ক্রল করার কারনে কিভাবে আপনার এনালাইটিক স্ক্রিপটি একটিভ  হয়ে যাই।
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
## ডিসকাস কমেন্টস্
ডিসকাসকে অলস করাটাও আগেরটার মতই

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
এটা অলস করলে আপনার বেনিফিট পেজ স্পিড আর সাইজে কোনো পরিবর্তন হবে না। 
