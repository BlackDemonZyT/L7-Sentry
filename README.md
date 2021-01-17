# L7-Sentry
 Java Console Application that will help you stop L7 harmfull attacks to your Apache or Nginx server.
 

# Must have
- Logging activated in your Apache / Nginx configuration
- Your website hosted on a VPS / Dedicated / Somewhere where Java will be able to execute system commands


# What will you check that will make this protection effective and less false-positives?
· Our checks on requester IPs will be:
1- Proxy/VPN check
2- Country check
3- Provider/ASN check
4- If in the same attack, the same IP sent different headers (like user-agent) more than 2 times
5- Repeating the same User-Agent with a LOT of different IPs


# How will this stop attacks to my web-server? Aren't L7 attacks undetectable?
You are right, L7 are not SO detectable, but theres ways to mitigate them without having a big impact on real visitors. Our software will detect traffic overload and will start collecting IPs, then, in a really optimized way, it will start checking if IPs are Proxies/VPN, what countries they come from, which provider, the IP-Ranges, etc... Based on all that data, our software will automaticlly IPSet (IPTables for huge amount of IPs) that malicious IPs, making that in their next connection attempt, all their packets are dropped in the networking layer, your system won't notice that they are trying to connect (even on the lowest and cheapest vpss).

You will be able to also add in a blocking-list what Countries, IP-Ranges and Providers you want to ALWAYS IPSet during attacks.


# I have an API on my Web-Server, will this block my legit customers?
The point of our software will be always having the less false-positives that we can, so you will be able to configurate WHICH request URI you want to protect, so you can except your API request points from the protection.
