---
layout: post
title:  "v-bind:src에서 이미지를 불러오지 못할때"
date:   2020-04-11 22:18:01 -0500
comments: true
categories: vue
sitemap :
  changefreq : daily
  priority : 1.0
---

이미지를 vue에서 가져올때
``` javascript
<img src="@/assets/images/test.jpg">
```
라고 작성후 크롬 개발자모드로 확인하면
``` javascript
<img src="data:image/jpeg;base64,/9j/4AASEw8UHRofHh0aH...n3P/9k=">
```
소스는 변환되어 보이지만 이미지는 정상적으로 보입니다.<br><br>

그러나,
``` javascript
<img :src="`@/assets/images/test.jpg`">
```
src 속성을 바인딩 하고 크롬 개발자모드로 확인하면
``` javascript
<img :src="`@/assets/images/test.jpg`">
```
소스가 그대로 보이고 이미지는 화면에 나타나지 않습니다.<br><br>


이럴때 간단한 해결책은 require안에 이미지 경로를 넣어주는 것입니다.

``` javascript
<img :src="require(`@/assets/images/test.jpg`)"

또는
<img :src="require(`@/assets/images/${imgURL}`)" 
```
