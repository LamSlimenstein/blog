---
layout: post
title: "Proxy config in Bash, NPM, Bower, Atom, Git & Ionic"
date: 2017-01-05
categories:
  - Web
  - Proxy
description: 
image: https://source.unsplash.com/BW0vK-FA3eg/2000x1000
image-sm: https://source.unsplash.com/BW0vK-FA3eg/500x300
preview: https://source.unsplash.com/BW0vK-FA3eg/2000x1000
---

Sometimes when you are building stuff behind huge networks like universities and
corporates, you often face proxy configuration issues with many applications
like NPM, Bower, Ionic, Git, Atom and Linux Bash itself. This article focuses on
resolving these issues.

### Linux Bash

##### With Authentication

{% highlight bash linenos %}

export http_proxy='http://username:password@[Your Proxy]:[Proxy Port]/'    
export https_proxy='http://username:password@[Your Proxy]:[Proxy Port]/'
export ftp_proxy='http://username:password@[Your Proxy]:[Proxy Port]/'

{% endhighlight %}

##### Without Authentication

{% highlight bash linenos %}

export http_proxy='http://[Your Proxy]:[Proxy Port]'    
export https_proxy='http://[Your Proxy]:[Proxy Port]'
export ftp_proxy='http://[Your Proxy]:[Proxy Port]'

{% endhighlight %}

##### View Proxy

{% highlight bash linenos %}

env | grep -i proxy

{% endhighlight %}

##### Remove proxy

{% highlight bash linenos %}

unset http_proxy
unset https_proxy
unset ftp_proxy
//these commands disable the proxy, temporarily for that particular bash session.

{% endhighlight %}


### NPM

##### With Authentication

{% highlight bash linenos %}

npm config set proxy "http://username:password@[Your Proxy]:[Proxy Port]/"
npm config set https-proxy "http://username:password@[Your Proxy]:[Proxy Port]/"

{% endhighlight %}



##### Without Authentication

{% highlight bash linenos %}

npm config set https-proxy http://[Your Proxy]:[Proxy Port]
npm config set proxy http://[Your Proxy]:[Proxy Port]

{% endhighlight %}


##### View Proxy

{% highlight bash linenos %}

npm config get https-proxy
npm config get proxy

{% endhighlight %}


##### Remove proxy

{% highlight bash linenos %}

npm config delete https-proxy
npm config delete proxy

//or

npm config set https-proxy null
npm config set proxy null

{% endhighlight %}


### Bower

##### With Authentication

{% highlight bash linenos %}

//add the lines to `.bowerrc`
"proxy":"http://username:password@[Your Proxy]:[Proxy Port]/"
"https-proxy":"http://username:password@[Your Proxy]:[Proxy Port]/"

{% endhighlight %}


##### Without Authentication

{% highlight bash linenos %}

// add the lines to `.bowerrc`
"proxy":"http://[Your Proxy]:[Proxy Port]"
"https-proxy":"http://[Your Proxy]:[Proxy Port]"

{% endhighlight %}


##### View Proxy

{% highlight bash linenos %}

cat .bowerrc

{% endhighlight %}


##### Remove proxy

{% highlight bash linenos %}

// edit and remove the lines from `.bowerrc` added earlier

{% endhighlight %}


### Atom

##### With Authentication

{% highlight bash linenos %}

apm config set proxy "http://username:password@[Your Proxy]:[Proxy Port]/"
apm config set https-proxy "http://username:password@[Your Proxy]:[Proxy Port]/"

{% endhighlight %}



##### Without Authentication

{% highlight bash linenos %}

apm config set https-proxy http://[Your Proxy]:[Proxy Port]
apm config set proxy http://[Your Proxy]:[Proxy Port]

{% endhighlight %}


##### View Proxy

{% highlight bash linenos %}

apm config get https-proxy
apm config get proxy

{% endhighlight %}


##### Remove proxy

{% highlight bash linenos %}

apm config delete https-proxy
apm config delete proxy

//or

apm config set https-proxy null
apm config set proxy null

{% endhighlight %}


### Git

##### With Authentication

{% highlight bash linenos %}

git config --add http.proxy "http://username:password@[YourProxy]:[ProxyPort]/"
git config --add https.proxy "http://username:password@[YourProxy]:[ProxyPort]/"

{% endhighlight %}


##### Without Authentication

{% highlight bash linenos %}

git config --add http.proxy http://[YourProxy]:[ProxyPort]
git config --add https.proxy http://[YourProxy]:[ProxyPort]

{% endhighlight %}


##### View Proxy

{% highlight bash linenos %}

git config --get http.proxy
git config --get https.proxy

{% endhighlight %}


##### Remove proxy

{% highlight bash linenos %}

git config --unset http.proxy
git config --unset https.proxy

{% endhighlight %}


### Ionic

##### With Authentication

{% highlight bash linenos %}

//You can add proxy along with the a particular serve
PROXY="http://username:password@[YourProxy]:[ProxyPort]/" ionic start [your app]

{% endhighlight %}


##### Without Authentication

{% highlight bash linenos %}

//You can add proxy along with the a particular serve
PROXY=http://[Your Proxy]:[Proxy Port] ionic start [your app]

{% endhighlight %}

*This post will be updated regularly with changes in configurations and new frameworks.*

*Comment below for any suggestions and framework/language requests.*

This is the [Medium article](https://medium.com/@magician03/proxy-config-in-bash-npm-bower-atom-git-ionic-56b545b76a6d) for this post