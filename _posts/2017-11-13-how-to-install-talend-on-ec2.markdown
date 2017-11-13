---
layout: post
title:  "How to install Talend on EC2"
date:   2017-11-13 22:41:40 +0100
categories: talend ec2
---
This article explains how to install Talend ESB on an EC2 machine.

Recommended instance type is a t2.medium with 2 vCPUs and 4 GiB memory:

![EC2 Talend Requirement]({{ "assets/ec2-talend-requirement.png" | absolute_url }})

ssh into the machine, and then install JDK 8

{% highlight console %}
sudo apt-get update
sudo apt-get install openjdk-8-jre
{% endhighlight %}

Environment variable `JAVA_HOME` must be set because Talend Runtime will first look out for Java installation.

Execute below command to find out alternative Java path.

{% highlight console %}
sudo update-alternatives --config java
{% endhighlight %}

Select path of preferred installation and update environment file by adding below code.

{% highlight console %}
sudo vi /etc/environment
JAVA_HOME="/usr/lib/jvm/java-8-oracle"
{% endhighlight %}

Reload file and test.

{% highlight console %}
source /etc/environment
echo $JAVA_HOME
{% endhighlight %}

I am using Cyberduck to send the zipped Runtime_ESBSE to EC2 server:

![Runtime_ESB]({{ "assets/runtime_esb.png" | absolute_url }})

Install and unzip Runtime ESBSE on server.

{% highlight console %}
sudo apt-get update
sudo apt-get install unzip
unzip Runtime_ESBSE.zip
rm Runtime_ESBSE.zip
{% endhighlight %}

Execute trun command to launch runtime environment. 

{% highlight console %}
cd Runtime_ESBSE/container/bin
./trun
{% endhighlight %}

![Karaf]({{ "assets/karaf.png" | absolute_url }})

We are ready to deploy Talend ESB RESTful services to Talend Runtime environment.
