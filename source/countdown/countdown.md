---
title: 倒数日
date: 2020-05-15 18:51:55
permalink: /countdown
---

<div id="today"><b>您的浏览器不支持此功能</b></div>

- <div id="count1"><b>请使用现代浏览器访问此页面</b></div>
- <div id="count2"><b>请使用现代浏览器访问此页面</b></div>
- <div id="count3"><b>请使用现代浏览器访问此页面</b></div>
- <div id="count4"><b>请使用现代浏览器访问此页面</b></div>
- <div id="count5"><b>请使用现代浏览器访问此页面</b></div>
    * 艺考此处特指高考美术与设计学类专业统考
- <div id="count6"><b>请使用现代浏览器访问此页面</b></div>
- <div id="count7"><b>请使用现代浏览器访问此页面</b></div>
- <div id="count8"><b>请使用现代浏览器访问此页面</b></div>
- <div id="count9"><b>请使用现代浏览器访问此页面</b></div>
***日期以官方公布的为准，未公布的均为按往年惯例所推测的时间。数据可能更新不及时，仅供参考。***

<script>
let date = new Date();
document.getElementById("today").innerHTML = "今天是 " + date.getFullYear() + " 年 " + (date.getMonth() + 1) + " 月 " + date.getDate() + " 日";

let now = Date.now();
let djs = [[1591372800000, 2], [1593187200000, 2], [1594051200000, 3], [1594396800000, 3], 1607184000000, [1610121600000, 3], [1620403200000, 2], [1622995200000, 3], [1624032000000, 3]];
let text = ["2020年等级考", "2020年中考", "2020年高考", "2020年合格考", "2020年艺考*", "2021年春季高考", "2021年等级考", "2021年秋季高考", "2021年中考"];
for (let i = 0; i < djs.length; i++) {
    if (Array.isArray(djs[i])) {
        let timeto = Math.ceil((djs[i][0] - now) / 1000 / 3600 / 24);
        let timeend = Math.ceil((djs[i][0] + 86400000 * (djs[i][1] - 1) - now) / 1000 / 3600 / 24);
        if (timeto < 0 && timeend < 0) {
            document.getElementById("count" + (i+1).toString()).innerHTML = " <code>" + text[i] + "</code> 已经过去<b> " + -timeend + " </b>天";
        } else if (timeto > 0) {
            document.getElementById("count" + (i+1).toString()).innerHTML = "距离 <code>" + text[i] + "</code> 还剩<b><font color=\"red\"> " + timeto + " </font></b>天";
        } else {
            document.getElementById("count" + (i+1).toString()).innerHTML = "今天是<b><font color=\"red\"> " + text[i] + " </font></b>的日子";
        }
    } else {
        let timeto = Math.ceil((djs[i] - now) / 1000 / 3600 / 24);
        if (timeto < 0) {
            document.getElementById("count" + (i+1).toString()).innerHTML = " <code>" + text[i] + "</code> 已经过去<b> " + -timeto + " </b>天";
        } else if (timeto > 0) {
            document.getElementById("count" + (i+1).toString()).innerHTML = "距离 <code>" + text[i] + "</code> 还剩<b><font color=\"red\"> " + timeto + " </font></b>天";
        } else {
            document.getElementById("count" + (i+1).toString()).innerHTML = "今天是<b><font color=\"red\"> " + text[i] + " </font></b>的日子";
        }
    }
}
</script>
