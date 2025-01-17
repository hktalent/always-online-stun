# Always Online: STUN servers
![GitHub commit activity](https://img.shields.io/github/commit-activity/w/pradt2/always-online-stun?style=for-the-badge)
![GitHub last commit](https://img.shields.io/github/last-commit/pradt2/always-online-stun?style=for-the-badge)
![GitHub](https://img.shields.io/github/license/pradt2/always-online-stun?style=for-the-badge)

Have you ever thought: *Gosh, why isn't there a regularly updated, comprehensive list of publicly available STUN servers*?

**Well, this is it. A list of online STUN servers, refreshed hourly.**

## How to use
Hardcode this link [valid_hosts.txt](https://raw.githubusercontent.com/pradt2/always-online-stun/master/valid_hosts.txt) into your application, and use it anytime you need a fresh list of online STUN servers.

Or, if you don't want to rely on DNS resolution, use [valid_ipv4s.txt](https://raw.githubusercontent.com/pradt2/always-online-stun/master/valid_ipv4s.txt) for IPv4, and [valid_ipv6s.txt](https://raw.githubusercontent.com/pradt2/always-online-stun/master/valid_ipv6s.txt) for IPv6 addresses.

## FAQ

### But hard-coding of links is baaaad?!
Well, not exactly. Hard-coding of links which were never meant to be hard-coded is bad.
Here the situation is different. Since I recommend that users hard-code the links to the few specific files, I'll avoid doing anything that would make the link invalid (e.g. I won't change the name of the file, name of the repository, my Github username, etc.).

### But I still don't feel comfortable hard-coding any links...
Feel free to open an issue and let's discuss your specific needs.

### How often are the lists refreshed?
Hourly, you can see the timestamp of the last check in the commit message.

### What RFC spec do the servers conform to? 
As long as the server correctly responds to an RFC5389 `BINDING` request, it is judged as healthy. 
This is enough to establish the NAT mapping of a given socket. 

_Noteworthy_: the server does not need to respond with an alternate IP address to be judged as healthy.
This can be a problem if you need a server with full RFC5389/5780 NAT testing (endpoint mapping and filtering modes) capability.

If you need a list of servers that support RFC5389/5780 NAT testing, open an issue.

### What IP versions and transport protocols are tested?
IP versions 4 and 6. UDP and TCP.

### I noticed that the lists are shuffled on each check. Why?
Lazy/inconsiderate devs will tend to just grab the top-most link from the list (and TBF, can we blame them?).
By shuffling the list, I ensure that we don't end up spamming the same host forever.

### What servers are checked, and how can I add more publicly available servers?
The list is in `candidates.txt`. Feel free to create a PR adding more servers, or just open an issue and list them there.

### My server is on your list, and I don't like it. What can I do?
Open an issue, and it will be removed from the automated checks within 24 hours.

