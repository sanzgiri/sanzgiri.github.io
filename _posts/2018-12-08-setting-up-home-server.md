---
title: Setting up a home server
date: 2018-12-08 00:00:00 Z
permalink: "/setting-up-home-server"
layout: post
excerpt: Using DDNS to set up remote access to home server
---
### Using DDNS to set up remote access to home server

* Following instructions at <https://www.howtogeek.com/66438/how-to-easily-access-your-home-network-from-anywhere-with-ddns/>
* I selected DYNU as the Dynamic DNS Service provider and created an account with them: <https://www.dynu.com/en-US/>. This is a free service and you can get a domain (I chose `sanzgiri.freeddns.org`) and IPv4 address
* Remote SSH to your machine is as easy as

``` ssh -A ashutosh@sanzgiri.freeddns.org ```

* You can remotely suspend your machine using

```ssh -t ashutosh@sanzgiri.freeddns.org sudo systemctl suspend```

* You can remotely wake up your machine using

```wakeonlan -p 4343 <mac-address>```

* Note that you need to enable wakeonlan on your motherboard in your BIOS setup. wakeonlan is a perl utility available from 
<https://github.com/jpoliv/wakeonlan/blob/master/wakeonlan>. You can also the "Mocha WOL" app on iOS.
