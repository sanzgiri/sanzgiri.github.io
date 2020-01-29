---
title: Using ngrok
date: 2018-06-02 00:00:00 Z
permalink: "/using-ngrok"
layout: post
excerpt: Using ngrok for remote access to your home machine
---
### Using ngrok for remote access to your home machine

ngrok (https://ngrok.com/) is a great way to connect to a web server (e.g jupyter notebook server) on your home machine or simply ssh into it.
A basic account is free. When you register, you will get an authtoken. Use that to create a config file on your home machine:

```
ngrok authtoken <YOUR-AUTH-TOKEN>
```

This puts the authtoken in `~/.ngrok2/ngrok.yml`. Edit this file and add the following lines:

```
tunnels:
  http:
    proto: http
    addr: 8888
  ssh:
    proto: tcp
    addr: 22
```

Next, start ngrok using:
```
ngrok start --all
```

Once you do this, you get a monitoring display that lists the forwarding addresses. At this point, you can point your browser to `https://<your-address>.ngrok.io` to connect
to your Jupyter notebook.

To ssh to your machine, you will have to use the syntax: `ssh <user>@0.tcp.ngrok.io -p <xxxxx>` where `p` is the forwarding port you see on the monitoring screen.






