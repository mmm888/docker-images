# NSD

[NSD](https://www.nlnetlabs.nl/projects/nsd/about/) is an authoritative DNS name server.

**It is required to add "/etc/nsd/nsd.conf"**

```bash
cat <<'_EOF_'> /etc/nsd/nsd.conf
server:
...

zone:
...
_EOF_
```
