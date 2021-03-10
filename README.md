
```bash
host localhost
dig @localhost
dig -x 127.0.0.1
dig 10.10.in-addr.arpa. AXFR
```

```bash
forwarders {
  8.8.8.8;
  8.8.4.4;
};
```

```bash
zone "seems.localdomain.forward" IN {
  type master;
  file "db.localdomain";
};

zone "10.10.in-addr.arpa" IN {
  type master;
  file "db.10.10";
};
```

```bash
# Host-only Network
10.0.0.0/24
10.0.1.0/24
# (...)
10.0.9.0/24

# NAT Network
10.10.0.0/24      # Gateway: 10.10.0.1

# Pseudo Subnets
10.10.0.10-19     # Workspace #0 - Templates
10.10.5.10-199    # Workspace #5
10.10.10.10-199   # Workspace #10
# (...)
10.10.255.10-199  # Workspace #255
```
