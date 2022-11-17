---
layout: layouts/post.njk
title: "Use a different DNS server! "
date: 2022-11-17T17:25:45.533Z
---
Change your upstream DNS to 1.1.1.1 or the quad9 and use the blocking thing to encrypt urls going to isp. check network chuck video about adguard.



make sure that all your devices are going through the quad1 or quad9 address, you can do this on the router, per device, use pihole as your DHCP server if you are unable to change the DNS settings on your router, this will make sure your DNS is going through pihole and blocking everything. Check it using ipconfig -a to view your DNS ip which should be set to your pihole address or DNS server if done manually. 



Make sure you add IPV6 DNS as well as ipv4, I hadnt turned it on originally so IPV6 was running through the router and not secure via aud1 or quad9. So a lot of devices were missing it. 



Also, make sure you update pihole and upgrade your linux server on a regular basis. And check gravity lists to make sure it pulls down the latest entries from the ad list. You can add lots of lists to your block list section, but the more you add the more issues you may have down the line with websites being blocked that you may need. 



Always try to use a different DNS and not a standard one from the ISP or similar. 



Look more into DOH - DNS-over-HTTPS as this will encrypt traffic between ISP and you. not sure if the other ones do this. - https://dns.quad9.net/dns-query this is the one with DOH 



https://1.1.1.1/dns/

https://one.one.one.one/family/ (Scroll down here to see the different DNS servers available.