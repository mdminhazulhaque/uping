# uping

`uping` (URL Ping) automatically extracts hostname from HTTP/HTTPS/FTP/SSH URLs. Even it can also remove port numbers, username and URL parameters from the given URL.

We often copy URLs from browser address bar, or Skype chat messages or system logs. When they are prefixed and suffixed with protocols, ports, it makes us do some extra keystrokes to remove those "http://" and lots of URL parameters. `uping` tries its best to extract the significant hostname from the given URI.

## Usage

Use `uping` just like you use the `ping` command. Just put the URL as the first argument. So rest of the arguments will be passed to `ping` command internally. For example,

```bash
minhaz@kubuntu > uping https://mdminhazulhaque.io/projects.html -c 4
PING mdminhazulhaque.io (51.254.103.216) 56(84) bytes of data.
64 bytes from minhazulhaque.com (51.254.103.216): icmp_seq=1 ttl=45 time=200 ms
64 bytes from minhazulhaque.com (51.254.103.216): icmp_seq=2 ttl=45 time=202 ms
64 bytes from minhazulhaque.com (51.254.103.216): icmp_seq=3 ttl=45 time=200 ms
64 bytes from minhazulhaque.com (51.254.103.216): icmp_seq=4 ttl=45 time=221 ms

--- mdminhazulhaque.io ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3003ms
rtt min/avg/max/mdev = 200.063/206.096/221.866/9.148 ms
```

## More Examples

| url | extracted hostname |
|-----|--------------------|
| google.com | google.com |
| search.google.com | search.google.com |
| https://mdminhazulhaque.io | mdminhazulhaque.io |
| http://bits.mdminhazulhaque.io | bits.mdminhazulhaque.io |
| ftp://mdminhazulhaque.io | mdminhazulhaque.io |
| ssh://root@mdminhazulhaque.io | mdminhazulhaque.io |
| https://mdminhazulhaque.io/projects.html | mdminhazulhaque.io |
| https://en.wikipedia.org/wiki/Ping_(networking_utility) | en.wikipedia.org |
| http://a.very.long.hostname.at.example.com:8080/also/with/long/long/url/params.html | a.very.long.hostname.at.example.com |


## Feedback

Please post bugs or feedback in the issue tracker. Thanks for using this junk peice of script! (: