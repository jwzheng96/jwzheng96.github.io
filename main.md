---
layout: homepage
title: Jianwei Zheng's homepage
---

<table style="border-style:none">
<tbody style="border-style:hidden">
<tr>
  <td><img width="256px" src="{{site.baseurl}}/static/figure/jianweizheng.jpg"></td>
  <td>
    <h2>JianweiZheng 郑剑伟</h2>
    <p>PhD student</p>
    <p>Tsinghua University</p>
    <p>zhengjw19 [AT] mails [dot] tsinghua [dot] edu [dot] com</p>
    <p><a href="{{site.baseurl}}/static/files/jianweizheng_cv_en.pdf">Download my CV</a>
    (<a href="{{site.baseurl}}/static/files/jianweizheng_cv_zh.pdf">中文版</a>)</p>
  </td>

</tr>
</tbody>
</table>

I'm now a PhD student under the supervision of [Zhenhua Li](http://www.greenorbs.org/people/lzh/) in the School of Software, Tsinghua University (THU).
My research interests lie in the fields of mobile computing, cloud computing and deep learning.

    
## Publications

(* indicates co-primary and/or corresponding author)

- Yang Li, **Jianwei Zheng**, Zhenhua Li, Yunhao Liu, Feng Qian, Sen Bai, Yao Liu, Xianlong Xin. "Understanding the ecosystem and addressing the fundamental concerns of commercial MVNO" IEEE/ACM Transactions on Networking (TON), Vol. 28, No. 3, Jun. 2020, Pages 1364-1377. (SCI, Impact factor: 3.597) [[PDF]]({{site.baseurl}}/static/files/TON20_Xiaomi_MVNO.pdf)

    [![TON2020](https://img.shields.io/badge/TON-2020-brightgreen.svg)](https://dl.acm.org/journal/ton)

## Honors, Grants and Awards

+ Working on it!

## Teaching

* Operating Systems (Undergraduate Course). TA
    * Spring 2021
* Basic Computer Programming (Undergraduate Course). TA
    * Spring 2021
* Data Quality (Graduate Course). TA
    * Fall 2020

## Others

{% for post in site.posts %}
+ [{{ post.title }}]({{ site.baseurl }}{{ post.url }}) {{ post.date | date_to_string }}
{% endfor %}
