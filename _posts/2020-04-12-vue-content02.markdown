---
layout: post
title:  "vue에서 mCustomScrollbar 사용하기"
date:   2020-04-12 17:37:01 -0600
comments: true
categories: vue
sitemap :
  changefreq : daily
  priority : 1.0
---

홈페이지에 이쁜 스크롤바를 사용하고 싶을때 저는 주로 mCustomScrollbar를 사용합니다.<br>
일반 홈페이지에서는 jquery로 간단하게 사용할 수 있지만 vue에서는 설정도 싶지 않고 npm을 찾아봐도 찾을수가 없었습니다.<br>
그러다가 마침 npm에서 malihu-custom-scrollbar-plugin라는 것을 찾았습니다.<br>
mCustomScrollbar를 npm에서는 'malihu-custom-scrollbar-plugin'이라는 이름으로 제공하고 있습니다.<br><br>

vue에서 'malihu-custom-scrollbar-plugin'를 사용하기 위해서는 먼저 
``` javascript
npm install jquery
npm install imports-loader
npm install jquery-mousewheel
npm install malihu-custom-scrollbar-plugin
```
를 설치하시구요.<br><br>

아래와 같이 해주시면 일반 홈페이지에서 사용하셨던 mCustomSrollbar를 vue에서도 사용하실 수 있습니다.

``` javascript

<template>
  <div id="content01">
  </div>
</template>

<script>
import $ from 'jquery';
import 'imports-loader';
import 'jquery-mousewheel';
import 'malihu-custom-scrollbar-plugin';

export default {
    updated() {
    // mCustomScrollbar 소스
    $('#content01').mCustomScrollbar({
      scrollButtons: { enable: false },
      theme: 'dark',
      scrollbarPosition: 'outside',
    });
  },
}
</script>

<style>

</style>
```
