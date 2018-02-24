---
title: "获取地址栏某个参数"
categories: js
tags: url
---



获取地址栏某个参数

eg：

&nbsp;&nbsp;&nbsp;**&nbsp;[http://localhost/invoice/application/web/index.php?r=apply%2Fhistory&amp;year=2017](\&quot;http://localhost/invoice/application/web/index.php?r=apply%2Fhistory&amp;year=2017\&quot;)**
<pre style="\&quot;background-color:#2b2b2b;color:#a9b7c6;font-family:\'宋体\';font-size:15.8pt;\&quot;"><span style="\&quot;color:#cc7832;font-weight:bold;\&quot;">function </span><span style="\&quot;color:#ffc66d;\&quot;">GetQueryString</span>(name)
{
    <span style="\&quot;color:#cc7832;font-weight:bold;\&quot;">var </span>reg = <span style="\&quot;color:#cc7832;font-weight:bold;\&quot;">new </span>RegExp(<span style="\&quot;color:#6a8759;\&quot;">\"(^|&amp;)\"</span>+ name +<span style="\&quot;color:#6a8759;\&quot;">\"=([^&amp;]*)(&amp;|$)\"</span>)<span style="\&quot;color:#cc7832;\&quot;">;
</span><span style="\&quot;color:#cc7832;\&quot;">    </span><span style="\&quot;color:#cc7832;font-weight:bold;\&quot;">var</span>r = <span style="\&quot;color:#9876aa;\&quot;">window</span>.<span style="\&quot;color:#9876aa;\&quot;">location</span>.<span style="\&quot;color:#ffc66d;\&quot;">search</span>.<span style="\&quot;color:#ffc66d;\&quot;">substr</span>(<span style="\&quot;color:#6897bb;\&quot;">1</span>).<span style="\&quot;color:#ffc66d;\&quot;">match</span>(reg)<span style="\&quot;color:#cc7832;\&quot;">;
</span><span style="\&quot;color:#cc7832;\&quot;">    </span><span style="\&quot;color:#cc7832;font-weight:bold;\&quot;">if</span>(r!=<span style="\&quot;color:#cc7832;font-weight:bold;\&quot;">null</span>)<span style="\&quot;color:#cc7832;font-weight:bold;\&quot;">return  </span><span style="\&quot;color:#ffc66d;\&quot;">decodeURI</span>(r[<span style="\&quot;color:#6897bb;\&quot;">2</span>])<span style="\&quot;color:#cc7832;\&quot;">; </span><span style="\&quot;color:#cc7832;font-weight:bold;\&quot;">return null</span><span style="\&quot;color:#cc7832;\&quot;">;
</span>}</pre><pre style="\&quot;background-color:#2b2b2b;color:#a9b7c6;font-family:\'宋体\';font-size:15.8pt;\&quot;"><span style="\&quot;color:#ffc66d;\&quot;">alert</span>(<span style="\&quot;color:#ffc66d;\&quot;">GetQueryString</span>(<span style="\&quot;color:#6a8759;\&quot;">\'year\'</span>))<span style="\&quot;color:#cc7832;\&quot;">;</span></pre>

**就能拿到2017了**

