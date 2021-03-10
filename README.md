
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
zone "db.localdomain" IN {
  type master;
  file "db.localdomain";
};

zone "10.10.in-addr.arpa" IN {
  type master;
  file "db.10.10";
};
```
