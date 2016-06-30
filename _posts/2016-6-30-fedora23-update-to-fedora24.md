---
layout: post
title: Fedora 23 升级到 Fedora 24
---

Fedora前几天发布了新版本24；本帖纪录怎么从Fedora 23升级到Fedora 24。

基本来说Fedora的升级有两种方法，一种是使用基于GUI的工具，另一种是使用终端命令行。

本帖主要介绍命令行方法，官方建议使用的方法是 **dnf upgrade plugin**。

## 升级步骤：

### 确保Fedora 23的软件包为最新

{% highlight shell %}
$ sudo dnf upgrade --refresh
{% endhighlight %}

### 安装 dnf-plugin-system-upgrade

{% highlight shell %}
$ sudo dnf install dnf-plugin-system-upgrade
{% endhighlight %}

### 开始升级

{% highlight shell %}
$ sudo dnf system-upgrade download --releasever=24
{% endhighlight %}

你可以加入**--allowerasing**选项，意思是移除有问题的软件包。

### 重启完成升级

{% highlight shell %}
$ sudo dnf system-upgrade reboot
{% endhighlight %}