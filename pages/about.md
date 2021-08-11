---
layout: page
title: 关于作者
description: 代码丰富生活
keywords: shi qiang, 石强
comments: true
menu: 关于
permalink: /about/
---

海贼无情,人有情。  
0011,码世界。  
分分秒秒,看世界。  
热爱代码,爱生活。  

## 联系

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'mazhuang.org' %}
<li>
微信公众号：<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="https://panlongshouhu.github.io/shiqiang/assets/images/qrcode.png" alt="石强的博客" />
</li>
{% endif %}
</ul>


## Skill Keywords

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
