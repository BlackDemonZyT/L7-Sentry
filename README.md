# L7-Sentry
 Java Console Application that will help you stop L7 harmfull attacks to your Apache or Nginx server.

# Must have
- Logging activated in your Apache / Nginx configuration
- Your website hosted on a VPS / Dedicated / Somewhere where Java will be able to execute system commands

# How will this stop attacks to my web-server? Aren't L7 attacks undetectable?
You are right, L7 are not SO detectable, but theres ways to mitigate them without having a big impact on real visitors. Our software will detect traffic overload and will start collecting IPs, then, in a really optimized way, it will start checking if IPs are Proxies/VPN, what countries they come from, which provider, the IP-Ranges, etc... Based on all that data, our software will automaticlly IPSet (IPTables for huge amount of IPs) that malicious IPs, making that in their next connection attempt, all their packets are dropped in the networking layer, your system won't notice that they are trying to connect (even on the lowest and cheapest vpss).

You will be able to also add in a blocking-list what Countries, IP-Ranges and Providers you want to ALWAYS IPSet during attacks.
