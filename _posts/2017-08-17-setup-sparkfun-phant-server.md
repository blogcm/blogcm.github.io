---
layout: post
title: setup sparkfun phant server
---
1. github page can not vitualise privately served phant
  Currently I have setup a phant server at a virtual machine maintained by nectar, the installation is quite simple, just do: 
{% highlight bash %}
npm insall -g phant
{% endhighlight %}
  and everything is done. however, github pages provide only https, the self served sparkfun page works only on http. Turns out, a https site can never extract data from http site, which makes github page not able to visualise the data. 
  The first thing i tried was to change the phant server into a https server, this could be achieved by firstly obtain a self signed lisence:
{% highlight bash %}
openssl req -nodes -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365
{% endhighlight %}
following https://stackoverflow.com/questions/10175812/how-to-create-a-self-signed-certificate-with-openssl
then add the certificate infomation to _/usr/local/lib/node_modules/phant/lib/https/_server.js_
{% highlight js %}
pp.credentials = function() {

  return {
    cert: fs.readFileSync('/opt/certs/example.com.crt'),
    key: fs.readFileSync('/opt/certs/example.com.key')
  };
};
{% endhighlight %}



  EFI is considered to be the replacement for bios. run the following commands on debian machine:
{% highlight bash %}
grub-install /dev/sda5
update-grub
efibootmgr -c -d /dev/sda5 -p 1 -w -L debian -l \EFI\debian\grubx64.efi
efibootmgr --verbose
{% endhighlight %}
  It needs to be noticed that in some cases 1. the screen appears to be black 2. nothings was happening after seleting debian. for the two sympoton, just try to wait patiently, and perhapse try to increase the back light(f2).

2. use 
