---
date: 2013-01-29T22:03:06Z
title: "Sublime SFTP package"
---

I’ve become an addicted fan of the [Sublime Text editor](http://www.sublimetext.com/). This is the most amazing text editor I’ve worked with. It’s been already greatly described in other blogs (see, for example [here](http://1p1e1.tumblr.com/post/14262857223/9-reasons-you-must-install-sublime-text-2-code-like-a) and [here](http://robdodson.me/blog/2012/06/23/sublime-text-2-tips-and-shortcuts/)), so I am not going into the details about it’s cool features. What I want to write about is one it’s packages which I find particularly useful — [Sublime SFTP](http://wbond.net/sublime_packages/sftp).

This package is very convenient if you run your jobs on a remote machine or a computational cluster. It’s basic functions are transferring files to the remote machine via FTP, FTPS and SFTP. But due to Sublime key bindings (keyboard shortcuts) the whole process of synchronizing your files is very handy (you almost don’t need a mouse) and takes milliseconds. And more importantly, you don’t need any other software except Sublime to edit and synchronize your code — it’s an all-in-one product!

By default, Sublime SFTP free trial is indefinite (it’s not restricted to 30 days), but you will occasionally receive a message asking to buy a license. Once you buy a license and activate it, you will receive no messages.

As I said this package is very handy. Here is a snapshot of it’s features:

{{<figure src="/images/sublime.png">}}

On the negative side — to be honest the only problem I had with this package was ssh localhost authentication (I am tunneling my remote machine using an RSA token key, and then mapping it using my localhost). I am not sure whether all of this make any sense, but I hope more experienced guys will understand it! Anyway, whenever I wanted to SFTP to my remote machine my Sublime editor always showed an error message about failed localhost authentication. The solution to this problem turned out to be quite simple. Normally, what you need to do is to change one of your ssh settings in __~/.ssh/config__ (user configuration file) or __/etc/ssh_config__ (global system configuration file). To edit these files you will need to change their permissions — please have a look here on how to do this. In the files you need to uncomment or add __NoHostAuthenticationForLocalhost__ setting and change its value to __yes__ (for more description on ssh settings please look [here](http://linuxcommando.blogspot.co.uk/2008/10/how-to-disable-ssh-host-key-checking.html) and [here](http://linuxcommando.blogspot.co.uk/2008/10/how-to-disable-ssh-host-key-checking.html)):

NoHostAuthenticationForLocalhost yes

Once you’ve done that your Sublime SFTP should not show any error message about the localhost authorization.

Do you use this package a lot? Like it? Did you have any problems with it? Any tips about them? Please comment!
