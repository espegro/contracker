# contracker
contracker - tool for logging outbound tcp connections using eBPF

A simple rewrite of [tcpconnect](https://www.brendangregg.com/blog/2015-10-31/tcpconnect-tcpaccept-bcc.html)

Tested on RHEL8 and Fedora34+, needs python3-bcc

/etc/contracker.yaml may be used to configure port, uid or process name to be "muted" from the log.

The log file is written in JSONL format.

The provided unit file should work, but may run into SELinux issues writing to /var/log/

