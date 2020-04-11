---
layout: post
title:  "v-bind:src에서 이미지를 불러오지 못할때"
date:   2020-04-11 22:18:01 -0500
comments: true
categories: vue
---


간단한 해결책은 require안에 이미지 경로를 넣어주는 것입니다.

``` javascript
<img :src="require(`@/assets/img/clear.gif`)"

또는
<img :src="require(`@/assets/img/${imgURL}`)" 
```
