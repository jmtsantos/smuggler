# smuggler
Ansible scripts to setup a remote server with ICMP and DNS tunneling

## Running

Just edit and run the ansible role `ansible-playbook -i hosts/cloud.yaml smuggle.yaml`

### ptunnel

On the client run `ptunnel -p <ipsrv> -lp 9999 -da destination.com -dp 22`

### iodine

First, setup the following DNS records:

* A dnsa.domain.com > x.x.x.x
* NS n.domain.com > dnsa.domain.com

On the client run `iodine -I 50 -f -P password n.domain.com`

### References

[https://medium.com/@galolbardes/learn-how-easy-is-to-bypass-firewalls-using-dns-tunneling-and-also-how-to-block-it-3ed652f4a000](https://medium.com/@galolbardes/learn-how-easy-is-to-bypass-firewalls-using-dns-tunneling-and-also-how-to-block-it-3ed652f4a000)
[https://www.mit.edu/afs.new/sipb/user/golem/tmp/ptunnel-0.61.orig/web/](https://www.mit.edu/afs.new/sipb/user/golem/tmp/ptunnel-0.61.orig/web/)
