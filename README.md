# contracker
contracker - tool for logging outbound tcp connections using eBPF

A simple rewrite of [tcpconnect](https://www.brendangregg.com/blog/2015-10-31/tcpconnect-tcpaccept-bcc.html)

Tested on RHEL8 and Fedora34+, needs python3-bcc

/etc/contracker.yaml may be used to configure port, uid or process name to be "muted" from the log.

The log file is written in JSONL format.

The provided unit file should work, but may run into SELinux issues writing to /var/log/

May be used to log tcp-forwarding using SSH or to log network activity on a multi user machine.

Typical log format:

```
{ "timestamp": "2021-11-19 20:20:25.287887", "user": "espegro", "uid": "127040", "comm": "nc", "pid": "380740", "ipv": "6", "srcip": "2001:700:100:202::144", "dstip": "2001:700:100:12::61", "dstport": "22" }                              
```
