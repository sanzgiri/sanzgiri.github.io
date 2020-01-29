---
title: Using Aws Cloud9 On Home Server
date: 2018-02-01 00:00:00 Z
permalink: "/using-AWS-Cloud9-on-home-server"
layout: post
excerpt: Setting up AWS Cloud9 on your home server
---

## Setting up AWS Cloud 9 to ssh to your home Ubuntu server

### Prepare your home Ubuntu server

- Set up port forwarding on your home router. You want to forward tcp port 22. Ideally, you want to forward it to non-standard port (say, 2220). For now, to keep things simple (but perhaps insecure), I just forwarded it to 22. The process for doing this is router-specific. As part of doing this, you also have to reserve the IP address for your 

- Get the public ip address of your machine. There are several ways to do this: 
```shell
wget -qO- http://ipecho.net/plain ; echo
curl ipinfo.io/ip
```

- Install nodejs on your home server:
```shell
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```

- Set up permissions on your home directory:
```
sudo chmod u=rwx,g=rx,o=rx ~
```

- You need to have python v2.7 in your path (check how critical this requirement is and what happens if you have version v3.x instead)

### Setup on AWS

- Login to your AWS console at https://console.aws.amazon.com/cloud9/home?region=us-east-1 (or appropriate region)

- Click "Create Environment"

- Select "Connect and run in remote server (SSH)"

- Enter your login name on your server under "User"

- Enter your server's public IP which you found above, under "Host"

- Port is the port to which you forwarded port 22 of your server above.

- Copy SSH key to your clipboard. Create or append the key to file .ssh/authorized_keys

- Set permission on this file to 600
```
chmod 600 .ssh/authorized_keys
```

- Skip "Advanced Settings" for now

- Click "Next Step". Here you will be able to review your settings and launch your development environment. You will be asked to confirm whether some tools can be installed on your server. Go ahead and accept.

- Voila, in a few minutes, you will have an amazing IDE for remote development on your home server.
