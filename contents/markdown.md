---
title: মার্কডাউন ওয়েবসাইট
header: মার্কডাউন ওয়েবসাইট 
description: খুবই সাধারণ আর সরল ভাবে এটা ডিজাইন করা।কোন রকম জাভাস্ক্রিপ্ট আর থিম ছাড়াই। যাষ্ট _config.yml ও _layouts ব্যবহার করেই।
permalink: contents/markdown
layout: post
---
সবগুলোর বিবরন দিতে গেলে অনেক বড় হয়ে যাবে বিধায় সংক্ষেপে লিখেছি।
# প্রথম ধাপ (কনফিগারেশন)
শুরুতে একটি _config.yml ফাইল বানাইছি। এখানে তেমন কিছুই করি নাই শুধু এক লাইনে আমার ওয়েবসাইটের এড্রেসটি লিখছি। 
```
url: "https://....."
```
# দ্বিতীয় ধাপ (লেআউট)
যেহেতু আমি প্রতিটি ক্ষেত্রেই এইচটিএমএল এর পরিবর্তে মার্কডাউন ব্যবহার করবো  তাই  আমাকে বেশ কয়েকটি কাজ করতে হবে যাতে আমাকে একি জিনিস বার বার না লিখা লাগে । প্রথমত মার্কডাউনটি যেহেতু এইচটিএমএল এ কনভার্ট হবে তাই এইচটিএমএল এর একটি ডিফাল্ট পেইজ লেআউট তৈরি করলে সকল পেজে এই লেআউট আকারেই বের হবে। আমি সেজন্য _layouts নামে একটি  ফোল্ডার তৈরি করি এবপর সেখানে  default.html নামের একটিএইচটিএমএল ফাইল তৈরি করি।
```
<!doctype html>
```
## এইচটিএমএল এ বাংলা ভাষা যোগ
```
<html lang="bn">
```
হেডে UTF-8 character সেট 
```
<head>
    <meta charset="utf-8">
```    
সার্চ থিম কালার পরিবর্তন
```
    <meta name="theme-color" content="#f76497">
```
ডিভাইসের স্ক্রীন সাইজ অনুসারে রেন্ডার
```
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```
## ফেভিকন সেট
এসেটস্ ফোল্টারে ইমেজেস সাবফোল্ডার করে ৫১২ বর্গ পিক্সেলের ফেভিকন পিএনজি আপলোড করছি। 
```
    <link rel="icon" href="/assets/images/favicon.png" />
```
## পেইজ টাইটেল ও বিবরন
এরপর পেজ টাইটেল আর ডেসক্রিপশান দিছি। পেজ বিবরন উল্লেখ করাটা সিও এর ক্ষেত্রে ভাল।
 এসেটস্ এ সিএসএস ফোল্ডারে স্টাইল.সিএসএস শুরুতে এম্পটি রেখে এখানে লিংক যোগ করছি। পরে এগুলিকে মিনিমাইজ করছি সাইজ কমানোর জন্য।
 ```   
    <link rel="stylesheet" href="/assets/css/all.css" />
    <link rel="stylesheet" href="/assets/css/style.css" />

  </head>
 ```
## বডি হেডার
ফিক্সড মেনু ও সাইড ন্যাগিভিশনের কাজ করেছি।মেইনে শুধু content এড করছি। সাথে আমার পারসোনাল ফন্টাসামের আইন লিংক ইউজ করছি।
## ফুটার
```    
    <footer>
      <p>সোহেল খান©২০২১</p>
    </footer>
```
# তৃতীয় ধাপ (সিএসএস সেটাপ)
খুবই অল্প পরিসরে যেগুলি খুবই গুরুত্বপূর্ণ সেগুলিই শুধু ডিজাইন করছি।
```
html {
  font-size: 20px;
}
```
## মেইন কাস্টমাইজ
```
main {
  color: #000;
  background: #fff;
  font-size: 1.15rem;
  line-height: 1.618;
  display: flex;
  min-height: 100vh;
  flex-direction: column;
  flex: 1;
  margin: 0 auto;
  max-width: 45rem;
  padding: 0 .5rem;
  overflow-x: hidden;
	word-break: break-word;
	overflow-wrap: break-word;
}
```
## হেডার কাস্টমাইজ
``` 
header {
    width: 100%;
    height: 50px;
    font-weight: 20px;
    line-height: 50px;
    text-align: center;
    background-color: #f76497;
    position: fixed;
    top: 0;
}
```

## ফন্ট অসাম এড
 নিজের মত করে কাস্টমাইজ করছি। এমনকি ওয়েবফন্টগুলিও এডিট করে একদম ছোট করে ফেলছি।

## টেক্সএরিয়া কাস্টমাইজ
```

textarea {
  width: 80%
}
```
## মোবাইল স্ক্রিন কাস্টমাইজ
মোবাইল স্ক্রিনে সাইড মেনুর জন্য মিডিয়া অন করছি
ডিসপ্লে ছোট বড় করে চেক করে দেখুন।


## হেডিং কাস্টমাইজ
```
h1, h2 {
	clear: both;
  font-weight: bold;
}

h1 {
	font-size: 1.6em;
        color: #778899;
}

h2 {
	font-size: 1.5em;
           color: #778899;
}
```

## ব্লককোট কাস্টমাইজ
```
blockquote {
    margin-left: 2em;
    margin-bottom: 2rem;
    margin-top: 2rem;
    padding: .4rem .8rem;
    border-left: .35rem solid green;
    color: red;
    font-style: italic;
}

```
## কোড কাস্টমাইজ
```
pre {
        overflow: auto; 
	padding: 20px;
	overflow: auto;
	max-height: 300px;
	background: #000;
	color: #fff;
}
```
ব্যাস সাইটির ফ্রেম পুরাপুরি কমপ্লিট। এখন শুধু মার্কডাউন এড করলেই সাইটটি ঠিকমত শো করবে।
# চতুর্থ ধাপ(মার্কডাউন ফাইল)
ইনডেক্স মার্কডাউন ফাইল তৈরি করে টাইটেল, হেডার,বর্ননা, পারমালিংক, লেআউট ডিফল্ট বা পোস্ট করছি।
```
---
tytle:
header:
description:
permalink:
layout:
---
```
## কমেন্টস অন (লেজি লোড)
কমেন্ট এ ল্যাজি ইফেক্ট জাভা স্ক্রিপ্ট ইউজ করছি যেহেতু আমি চাই না পেজে কোনো জিএস থাকে।
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

 স্ক্রল করে কিছুক্ষন অপেক্ষা করলে কমেন্টস দেখতে পারবেন। লেজি করার কারনে পেজ স্পিডে কোন সমস্যা হবে না।Performance চেক করতে পারেন [লাইটহাউজে](https://lighthouse-dot-webdotdevsite.appspot.com//lh/html?url=https%3A%2F%2F60z.github.io%2F)। [gtmetrix](https://gtmetrix.com/reports/60z.github.io/aQzXZHAY/)
জিটিম্যাট্রিক্সে চেক করতে পারেন ওয়েবসাইটের সাইজ ১০ কেবির নিচে  [জিটিম্যাট্রিক্স](https://gtmetrix.com/har.html?inputUrl=/reports/60z.github.io/aQzXZHAY/net.harp&expand=true&validate=false)।
৫১২কেবি ক্লাবে এই ওয়েবসাইটটি গ্রীন টিমে আছে [512kb.club](https://512kb.club/) ।
গিটহাবে আমার ওপেন সোর্স রিপুটা দেখতে পারেন [60z](https://github.com/60z/60z.github.io/)।
এই পেজের পারফরম্যান্স ১০০% ডিসকাস অন করার পরেও। চেক করে দেখতে পারেন [এখানে](https://lighthouse-dot-webdotdevsite.appspot.com//lh/html?url=https%3A%2F%2F60z.github.io%2Fcontents%2Fmarkdown) ।
