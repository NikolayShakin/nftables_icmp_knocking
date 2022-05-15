# nftables icmp-knocking
Basic nftables ruleset with ICMP knocking implementation.

ICMP knocking is a fast way to add your current IP address into white list of your firewall.

### What is the problem? 

Ususaly you want to keep your ssh port closed for any IP address 
except few tusted addresses. 
It fair enough but it cause a problem if you are not on the trussted IP
you can't access your server.

### How does ICMP-knocking work?

If you want to access your server from an unknown IP address 
you just send to your server exact number of ICMP packets with a specific size. 
Done, your address is on the white list for ssh with a timeout you specified. 
For example, send 13 packets of 666 bytes size "ping -s 666 -c 13". It's that simple.

### Security notes

It's a very effective and light-weight tool to have access to your server 
with no endless brutforce attacks on it. ICMP-knocking is not too popular protection
and it have no fingerprint so it's a rare case that the attacker will try to hack it. 
As you might see  the idea is a quite simple and icmp-knocking can be hacked easily 
if malicious users can see your traffic.
A side effect of this drawback is that if you'll see someone go through your ICMP-knocking
rule - it's a problem and it is almost guaranteed they can sniff your traffic.
You have to consider all the risks and use ICMP-knocking as an addition 
to other security levels and not instead of them.
