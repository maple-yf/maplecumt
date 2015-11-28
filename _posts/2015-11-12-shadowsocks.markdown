---
layout: post
title:  "安装 ShadowScoks"
date:   2015-11-12 15:30:00
categories: Daily
---
# 前言 #
ShadowScoks是一个非常易用的翻墙工具，把它安装在自己的VPS上，就可以随心所欲的上网啦！
# 安装 #
输入su进入root。
分别复制以下命令到命令行：

<div class="highlight" style="background: #ffffff"> wget <span style="color: #333333">--</span>no<span style="color: #333333">-</span>check<span style="color: #333333">-</span>certificate https<span style="color: #333333">:</span><span style="color: #888888">//raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh</span>
 chmod <span style="color: #333333">+</span>x shadowsocks.sh
 .<span style="color: #333333">/</span>shadowsocks.sh <span style="color: #0000DD; font-weight: bold">2</span><span style="color: #333333">&gt;&amp;</span><span style="color: #0000DD; font-weight: bold">1</span> <span style="color: #333333">|</span> tee shadowsocks.log
</div>

执行最后一条命令之后，出现一下界面：

![](https://raw.githubusercontent.com/maplecumt/maplecumt.github.io/master/images/2015-11-12-shadowsocks/ss1.png)

输入密码即可。并回车，再次回车，确认安装。

![](https://raw.githubusercontent.com/maplecumt/maplecumt.github.io/master/images/2015-11-12-shadowsocks/ss3.png)

安装失败，出现错误提示：

<div class="highlight" style="background: #ffffff">.<span style="color: #333333">/</span>shadowsocks.sh<span style="color: #333333">:</span> line <span style="color: #0000DD; font-weight: bold">111</span><span style="color: #333333">:</span>  <span style="color: #0000DD; font-weight: bold">6396</span> Segmentation fault      (core dumped) apt<span style="color: #333333">-</span>get <span style="color: #333333">-</span>y update
Reading package lists....<span style="color: #333333">/</span>shadowsocks.sh<span style="color: #333333">:</span> line <span style="color: #0000DD; font-weight: bold">111</span><span style="color: #333333">:</span>  <span style="color: #0000DD; font-weight: bold">6461</span> Segmentation fault      (core dumped) apt<span style="color: #333333">-</span>get <span style="color: #333333">-</span>y install python python<span style="color: #333333">-</span>dev python<span style="color: #333333">-</span>pip curl wget unzip gcc swig automake make perl cpio
</div>


分别执行 (core dumped)后面的语句
<div class="highlight" style="background: #ffffff">apt<span style="color: #333333">-</span>get <span style="color: #333333">-</span>y update
apt<span style="color: #333333">-</span>get <span style="color: #333333">-</span>y install python python<span style="color: #333333">-</span>dev python<span style="color: #333333">-</span>pip curl wget unzip gcc swig automake make perl cpio
</div>

然后，重新执行:

{% highlight ruby linenos %}
./shadowsocks.sh 2>&1 | tee shadowsocks.log
{% endhighlight %}

等待5分钟左右，即可安装成功，安装成功之后就会通过屏幕输出，您的IP地址，端口，密码，及加密方式。

![](https://raw.githubusercontent.com/maplecumt/maplecumt.github.io/master/images/2015-11-12-shadowsocks/ss4.png)

如果您想多用户使用，请配置 /etc/shadowsocks.json 这个文件。配置模版：

<div class="highlight" style="background: #ffffff">{
    <span style="background-color: #fff0f0">&quot;server&quot;</span><span style="color: #333333">:</span><span style="background-color: #fff0f0">&quot;your_server_ip&quot;</span>,
    <span style="background-color: #fff0f0">&quot;local_address&quot;</span><span style="color: #333333">:</span> <span style="background-color: #fff0f0">&quot;127.0.0.1&quot;</span>,
    <span style="background-color: #fff0f0">&quot;local_port&quot;</span><span style="color: #333333">:</span><span style="color: #0000DD; font-weight: bold">1080</span>,
    <span style="background-color: #fff0f0">&quot;port_password&quot;</span><span style="color: #333333">:</span>{
         <span style="background-color: #fff0f0">&quot;8989&quot;</span><span style="color: #333333">:</span><span style="background-color: #fff0f0">&quot;password0&quot;</span>,
         <span style="background-color: #fff0f0">&quot;9001&quot;</span><span style="color: #333333">:</span><span style="background-color: #fff0f0">&quot;password1&quot;</span>,
         <span style="background-color: #fff0f0">&quot;9002&quot;</span><span style="color: #333333">:</span><span style="background-color: #fff0f0">&quot;password2&quot;</span>,
         <span style="background-color: #fff0f0">&quot;9003&quot;</span><span style="color: #333333">:</span><span style="background-color: #fff0f0">&quot;password3&quot;</span>,
         <span style="background-color: #fff0f0">&quot;9004&quot;</span><span style="color: #333333">:</span><span style="background-color: #fff0f0">&quot;password4&quot;</span>
    },
    <span style="background-color: #fff0f0">&quot;timeout&quot;</span><span style="color: #333333">:</span><span style="color: #0000DD; font-weight: bold">300</span>,
    <span style="background-color: #fff0f0">&quot;method&quot;</span><span style="color: #333333">:</span><span style="background-color: #fff0f0">&quot;aes-256-cfb&quot;</span>,
    <span style="background-color: #fff0f0">&quot;fast_open&quot;</span><span style="color: #333333">:</span> <span style="color: #007020">false</span>
}
</div>

Windows客户端下载地址：[https://shadowsocks.org/en/download/clients.html](https://shadowsocks.org/en/download/clients.html)
使用教程：[http://wiki.ssnode.co/index.php?option=com_content&view=article&id=4:about-your-home-page&catid=9&Itemid=101](http://wiki.ssnode.co/index.php?option=com_content&view=article&id=4:about-your-home-page&catid=9&Itemid=101)
使用shadowsocks时，必须要通过SSH连接上自己的VPS后才能代理成功。