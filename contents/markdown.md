---
title: মার্কডাউন ওয়েবসাইট
header: মার্কডাউন ওয়েবসাইট 
description: খুবই সাধারণ আর সরল ভাবে এটা ডিজাইন করা।কোন রকম জাভাস্ক্রিপ্ট আর থিম ছাড়াই।
permalink: contents/markdown
layout: post
---
এটা বানাতে আমি শুধু _congif.yml, _layout আর  css এই তিনটি directory ব্যবহার করছি। খুবই সাধারন তবে সবকিছুই ১০০% টপ পারফরম্যান্সড  ওয়েবসাইট। [লাইটহাউজে](https://lighthouse-dot-webdotdevsite.appspot.com//lh/html?url=https%3A%2F%2F60z.github.io) ঢুকে ডিটেইলস দেখতে পারেন। এমনকি ওয়েবসাইটটির সাইজ খুবই লাইট ২০ কেবির নিচে। [জিটিম্যাট্রিক্সে](https://gtmetrix.com/reports/60z.github.io/3UxJb7gS/) পুরাপুরি দেখতে পারবেন। 

# প্রথম ধাপ (কনফিগারেশন)
শুরুতে একটি `_config.yml` ফাইল বানাইছি। এখানে তেমন কিছুই করি নাই শুধু এক লাইনে আমার ওয়েবসাইটের এড্রেসটি লিখছি।
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
```
    <title>{{ page.title }}</title>
    <meta name="description" content="{{ page.description }}" />
 ```   
 এসেটস্ এ সিএসএস ফোল্ডারে স্টাইল.সিএসএস এম্পটি রেখে এখানে লিংক যোগ করছি। 
 ```   
    <link rel="stylesheet" href="/assets/css/all.css" />
    <link rel="stylesheet" href="/assets/css/style.css" />

  </head>
 ```
## বডি হেডার
ফিক্সড মেনুর জন্য হেডারে এই কোডটি এড করছি। সাথে টাইপরাইডার ইফেক্ট এড করা।
 ```
 <header>
        <figure class="brand typewriter typing-erase">সোহেল খান</figure>
        <nav class="menu">
            <input type="checkbox" id="menuToggle">
            <label for="menuToggle" class="menu-icon"><i class="fas fa-bars"></i></label>
            <ul>
                
                   <li><a  href="/"><i class="fas fa-home"></i> হোম</a> </li>
                   <li><a  href="/#"><i class="fas fa-code"></i> কোডিং</a> </li>
                   <li><a  href="/#"><i class="fas fa-briefcase"></i> কাজ</a> </li>
                   <li> <a  href="/contents/markdown"> <i class="fas fa-blog"></i> ব্লগ</a> </li>
            
            </ul>
        </nav>
    </header>
```
মেইনে শুধু content এড করছি। সাথে আমার পারসোনাল ফন্টাসামের আইন লিংক ইউজ করছি।
```
<p style="text-align:center;">  <a href="https://facebook.com/nahklehos" aria-label="Facebook" class="fab fa-facebook fa-2x"></a>
       <a href="https://twitter.com/nahklehos/" aria-label="Twitter" class="fab fa-twitter fa-2x"></a>
      <a href="https://linkedin.com/in/nahklehos" aria-label="Linkedin" class="fab fa-linkedin fa-2x"></a>
       <a href="https://github.com/60z" aria-label="Github" class="fab fa-github fa-2x"></a>
      <a href="https://gitlab.com/sohel.khan" aria-label="Gitlab" class="fab fa-gitlab fa-2x"></a>
      <a href="https://bitbucket.org/sohel_khan" aria-label="Bitbucket" class="fab fa-bitbucket fa-2x"></a>
      <a href="https://stackoverflow.com/sohel.khan" aria-label="Stackoverflow" class="fab fa-stack-overflow fa-2x"></a>
      </p>
```
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

    line-height: 50px;

    text-align: center;

    background-color: #f76497;

    position: fixed;

        top: 0;

}

```
## টাইপরাইটার ইফেক্ট
```
.typewriter {
  color: #000;
  font-size: 1.5em;
  font-weight: 500;
  width: 0;
  max-width: max-content;
  overflow: hidden; 
  border-right: .6em solid transparent; /* The typwriter cursor */
  white-space: nowrap; /* Keeps the content on a single line */
  margin: 0; /* Gives that scrolling effect as the typing happens */
}

.typing-erase {
  animation: 
    4s typing-erase 4s steps(20, end) infinite,
    blink-caret .5s step-end infinite;
}

/* The type and erase effect */
@keyframes typing-erase {
  0% { width: 0 }
  50% { width: 100% }
  60%, 100% { width: 0 }
}

/* The typewriter cursor effect */
@keyframes blink-caret {
  from, to { border-color: transparent }
  50% { border-color: transparent }
}
```
## ফন্ট অসাম এড
ফট অসার নিজের মত করে কাস্টমাইজ করছি। এমনকি ওয়েবফন্টগুলিও এডিট করে একদম ছোট করে ফেলছি।
```
.fa,
.fas,
.far,
.fal,
.fad,
.fab {
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  display: inline-block;
  font-style: normal;
  font-variant: normal;
  text-rendering: auto;
  line-height: 1; }
  
.fa-2x {
  font-size: 2em; }

.fa-bars:before {
  content: "\f0c9"; }

.fa-blog:before {
  content: "\f781"; }

.fa-briefcase:before {
  content: "\f0b1"; }

.fa-bitbucket:before {
  content: "\f171"; }

.fa-code:before {
  content: "\f121"; }

.fa-home:before {
  content: "\f015"; }

.fa-facebook:before {
  content: "\f09a"; }

.fa-instagram:before {
  content: "\f16d"; }

.fa-github:before {
  content: "\f09b"; }

.fa-gitlab:before {
  content: "\f296"; }

.fa-stack-overflow:before {
  content: "\f16c"; }

.fa-twitter:before {
  content: "\f099"; }

.fa-linkedin:before {
  content: "\f08c"; }


@font-face {
  font-family: 'Font Awesome 5 Free';
  font-style: normal;
  font-weight: 900;
  font-display: block;
   src: url("../webfonts/fa-solid-900.eot");
  src: url("../webfonts/fa-solid-900.eot?#iefix") format("embedded-opentype"), url("../webfonts/fa-solid-900.woff2") format("woff2"), url("../webfonts/fa-solid-900.woff") format("woff"), url("../webfonts/fa-solid-900.ttf") format("truetype"), url("../webfonts/fa-solid-900.svg#fontawesome") format("svg"); }

.fa,
.fas {
  font-family: 'Font Awesome 5 Free';
  font-weight: 900; }

 
@font-face {
  font-family: 'Font Awesome 5 Brands';
  font-style: normal;
  font-weight: 400;
  font-display: block;
  src: url("../webfonts/fa-brands-400.eot");
  src: url("../webfonts/fa-brands-400.eot?#iefix") format("embedded-opentype"), url("../webfonts/fa-brands-400.woff2") format("woff2"), url("../webfonts/fa-brands-400.woff") format("woff"), url("../webfonts/fa-brands-400.ttf") format("truetype"), url("../webfonts/fa-brands-400.svg#fontawesome") format("svg"); }

.fab {
  font-family: 'Font Awesome 5 Brands';
  font-weight: 400; }
```
## টেক্সএরিয়া কাস্টমাইজ
```

textarea {
  width: 80%
}
```
## মোবাইল স্ক্রিন কাস্টমাইজ
মোবাইল স্ক্রিনে সাইড মেনুর জন্য মিডিয়া অন করছি
```
@media screen and (max-width: 768px) {

    .menu {

        width: 100%;

        height: auto;

    }

    .menu ul {

        display: block;

        max-height: 0;

    	overflow: hidden;

    	-webkit-transition: max-height 0.3s;

    	-moz-transition: max-height 0.3s;

        -ms-transition: max-height 0.3s;

        -o-transition: max-height 0.3s;

    	transition: max-height 0.3s;

    }

    li a {

        text-align: left;

        width: 100%;

        height: auto;

        background-color: #f773a1;

        padding: 10px 0px 10px 5%;

    }

    .menu-icon {

        width: 100px;

        height: inherit;

        display: block;

        position: absolute;

        top: 0;

        right: 0;

        line-height: 60px;

    }

    #menuToggle:checked ~ ul {

        max-height: 350px;

    }

    .menu-icon i {

        font-size: 1.7em;

    }

  textarea,

  select,

  input {

    width: 100%;

  }

}

```
## হেডিং কাস্টমাইজ
```
h1, h2 {
	clear: both;
  font-weight: bold;
}

h1 {
	font-size: 2em;
        color: green;
}

h2 {
	font-size: 1.6em;
           color: #778899;
}


```

```
i.hash {
  font-size: 0.8em;
  color: blue;
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
	font-size: 14px;
	background: #000;
	color: #fff;
}
```
ব্যাস সাইটির ফ্রেম পুরাপুরি কমপ্লিট। এখন শুধু মার্কডাউন এড করলেই সাইটটি এভাবে শো করবে।
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
## কমেন্টস অন



কমেন্ট এ ল্যাজি ইফেক্ট জাভা স্ক্রিপ্ট ইউজ করছি যেহেতু আমি চাই না পেজে কোনো জেএস থাকে। স্ক্রল করে কিছুক্ষন অপেক্ষা করলে কমেন্টস দেখতে পারবেন। লেজি করার কারনে পেজ স্পিডে কোন সমস্যা হবে না। কোনো মতামত থাকলে  কমেন্টস করতে পারেন।
