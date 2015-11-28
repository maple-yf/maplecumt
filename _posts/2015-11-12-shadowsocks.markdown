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
<<<<<<< HEAD


<div class="highlight" style="background: #272822"><span style="background-color: #f0f0f0; padding: 0 5px 0 5px">1</span> <span style="color: #f8f8f2">.</span><span style="color: #f92672">/</span><span style="color: #f8f8f2">shadowsocks.sh</span><span style="color: #f92672">:</span> <span style="color: #f8f8f2">line</span> <span style="color: #ae81ff">111</span><span style="color: #f92672">:</span> <span style="color: #ae81ff">6396</span> <span style="color: #f8f8f2">Segmentation</span> <span style="color: #f8f8f2">fault</span> <span style="color: #f8f8f2">(core</span> <span style="color: #f8f8f2">dumped)</span> <span style="color: #f8f8f2">apt</span><span style="color: #f92672">-</span><span style="color: #f8f8f2">get</span> <span style="color: #f92672">-</span><span style="color: #f8f8f2">y</span> <span style="color: #f8f8f2">update</span> <span style="color: #f8f8f2">Reading</span> <span style="color: #f8f8f2">package</span> <span style="color: #f8f8f2">lists....</span><span style="color: #f92672">/</span><span style="color: #f8f8f2">shadowsocks.sh</span><span style="color: #f92672">:</span> <span style="color: #f8f8f2">line</span> <span style="color: #ae81ff">111</span><span style="color: #f92672">:</span> <span style="color: #ae81ff">6461</span> <span style="color: #f8f8f2">Segmentation</span> <span style="color: #f8f8f2">fault</span> <span style="color: #f8f8f2">(core</span> <span style="color: #f8f8f2">dumped)</span> <span style="color: #f8f8f2">apt</span><span style="color: #f92672">-</span><span style="color: #f8f8f2">get</span> <span style="color: #f92672">-</span><span style="color: #f8f8f2">y</span> <span style="color: #f8f8f2">install</span> <span style="color: #f8f8f2">python</span> <span style="color: #f8f8f2">python</span><span style="color: #f92672">-</span><span style="color: #f8f8f2">dev</span> <span style="color: #f8f8f2">python</span><span style="color: #f92672">-</span><span style="color: #f8f8f2">pip</span> <span style="color: #f8f8f2">curl</span> <span style="color: #f8f8f2">wget</span> <span style="color: #f8f8f2">unzip</span> <span style="color: #f8f8f2">gcc</span> <span style="color: #f8f8f2">swig</span> <span style="color: #f8f8f2">automake</span> <span style="color: #f8f8f2">make</span> <span style="color: #f8f8f2">perl</span> <span style="color: #f8f8f2">cpio</span>
</div>


=======
{% highlight ruby linenos %}
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
chmod +x shadowsocks.sh
./shadowsocks.sh 2>&1 | tee shadowsocks.log
{% endhighlight %}
>>>>>>> parent of bb6ca74... Change highlight to sublimehighlight
执行最后一条命令之后，出现一下界面：

![](https://raw.githubusercontent.com/maplecumt/maplecumt.github.io/master/images/2015-11-12-shadowsocks/ss1.png)

输入密码即可。并回车，再次回车，确认安装。

![](https://raw.githubusercontent.com/maplecumt/maplecumt.github.io/master/images/2015-11-12-shadowsocks/ss3.png)

安装失败，出现错误提示：
<<<<<<< HEAD

<div class="highlight" style="background: #272822"><span style="background-color: #f0f0f0; padding: 0 5px 0 5px">1</span> <span style="color: #f8f8f2">wget</span> <span style="color: #f92672">--</span><span style="color: #f8f8f2">no</span><span style="color: #f92672">-</span><span style="color: #f8f8f2">check</span><span style="color: #f92672">-</span><span style="color: #f8f8f2">certificate</span> <span style="color: #f8f8f2">https</span><span style="color: #f92672">:</span><span style="color: #75715e">//raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh chmod +x shadowsocks.sh ./shadowsocks.sh 2&gt;&amp;1 | tee shadowsocks.log</span>
</div>


分别执行 (core dumped)后面的语句
<div class="highlight" style="background: #ffffff">apt<span style="color: #333333">-</span>get <span style="color: #333333">-</span>y update
apt<span style="color: #333333">-</span>get <span style="color: #333333">-</span>y install python python<span style="color: #333333">-</span>dev python<span style="color: #333333">-</span>pip curl wget unzip gcc swig automake make perl cpio
</div>
=======
{% highlight ruby linenos %}
./shadowsocks.sh: line 111:  6396 Segmentation fault      (core dumped) apt-get -y update
Reading package lists..../shadowsocks.sh: line 111:  6461 Segmentation fault      (core dumped) apt-get -y install python python-dev python-pip curl wget unzip gcc swig automake make perl cpio
{% endhighlight %}

分别执行 (core dumped)后面的语句
{% highlight ruby linenos %}
apt-get -y update
apt-get -y install python python-dev python-pip curl wget unzip gcc swig automake make perl cpio
{% endhighlight %}
>>>>>>> parent of bb6ca74... Change highlight to sublimehighlight

然后，重新执行:

<div class="highlight" style="background: #272822"><span style="background-color: #f0f0f0; padding: 0 5px 0 5px">1</span> <span style="color: #f8f8f2">.</span><span style="color: #f92672">/</span><span style="color: #f8f8f2">shadowsocks.sh</span> <span style="color: #ae81ff">2</span><span style="color: #f92672">&gt;&amp;</span><span style="color: #ae81ff">1</span> <span style="color: #f92672">|</span> <span style="color: #f8f8f2">tee</span> <span style="color: #f8f8f2">shadowsocks.log</span>
</div>

等待5分钟左右，即可安装成功，安装成功之后就会通过屏幕输出，您的IP地址，端口，密码，及加密方式。

![](https://raw.githubusercontent.com/maplecumt/maplecumt.github.io/master/images/2015-11-12-shadowsocks/ss4.png)

如果您想多用户使用，请配置 /etc/shadowsocks.json 这个文件。配置模版：

<<<<<<< HEAD
<div class="highlight" style="background: #272822"><span style="background-color: #f0f0f0; padding: 0 5px 0 5px"> 1</span> <span style="color: #f8f8f2">{</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px"> 2</span>     <span style="color: #e6db74">&quot;server&quot;</span><span style="color: #f92672">:</span><span style="color: #e6db74">&quot;your_server_ip&quot;</span><span style="color: #f8f8f2">,</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px"> 3</span>     <span style="color: #e6db74">&quot;local_address&quot;</span><span style="color: #f92672">:</span> <span style="color: #e6db74">&quot;127.0.0.1&quot;</span><span style="color: #f8f8f2">,</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px"> 4</span>     <span style="color: #e6db74">&quot;local_port&quot;</span><span style="color: #f92672">:</span><span style="color: #ae81ff">1080</span><span style="color: #f8f8f2">,</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px"> 5</span>     <span style="color: #e6db74">&quot;port_password&quot;</span><span style="color: #f92672">:</span><span style="color: #f8f8f2">{</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px"> 6</span>          <span style="color: #e6db74">&quot;8989&quot;</span><span style="color: #f92672">:</span><span style="color: #e6db74">&quot;password0&quot;</span><span style="color: #f8f8f2">,</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px"> 7</span>          <span style="color: #e6db74">&quot;9001&quot;</span><span style="color: #f92672">:</span><span style="color: #e6db74">&quot;password1&quot;</span><span style="color: #f8f8f2">,</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px"> 8</span>          <span style="color: #e6db74">&quot;9002&quot;</span><span style="color: #f92672">:</span><span style="color: #e6db74">&quot;password2&quot;</span><span style="color: #f8f8f2">,</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px"> 9</span>          <span style="color: #e6db74">&quot;9003&quot;</span><span style="color: #f92672">:</span><span style="color: #e6db74">&quot;password3&quot;</span><span style="color: #f8f8f2">,</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px">10</span>          <span style="color: #e6db74">&quot;9004&quot;</span><span style="color: #f92672">:</span><span style="color: #e6db74">&quot;password4&quot;</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px">11</span>     <span style="color: #f8f8f2">},</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px">12</span>     <span style="color: #e6db74">&quot;timeout&quot;</span><span style="color: #f92672">:</span><span style="color: #ae81ff">300</span><span style="color: #f8f8f2">,</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px">13</span>     <span style="color: #e6db74">&quot;method&quot;</span><span style="color: #f92672">:</span><span style="color: #e6db74">&quot;aes-256-cfb&quot;</span><span style="color: #f8f8f2">,</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px">14</span>     <span style="color: #e6db74">&quot;fast_open&quot;</span><span style="color: #f92672">:</span> <span style="color: #f8f8f2">false</span>
<span style="background-color: #f0f0f0; padding: 0 5px 0 5px">15</span> <span style="color: #f8f8f2">}</span>
</div>

=======
{% highlight ruby linenos %}
{
    "server":"your_server_ip",
    "local_address": "127.0.0.1",
    "local_port":1080,
    "port_password":{
         "8989":"password0",
         "9001":"password1",
         "9002":"password2",
         "9003":"password3",
         "9004":"password4"
    },
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open": false
}
{% endhighlight %}
>>>>>>> parent of bb6ca74... Change highlight to sublimehighlight
Windows客户端下载地址：[https://shadowsocks.org/en/download/clients.html](https://shadowsocks.org/en/download/clients.html)
使用教程：[http://wiki.ssnode.co/index.php?option=com_content&view=article&id=4:about-your-home-page&catid=9&Itemid=101](http://wiki.ssnode.co/index.php?option=com_content&view=article&id=4:about-your-home-page&catid=9&Itemid=101)
使用shadowsocks时，必须要通过SSH连接上自己的VPS后才能代理成功。