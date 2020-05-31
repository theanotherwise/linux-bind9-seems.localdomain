```bash
for i in `cat 10.10.in-addr.arpa  | grep -Po " [a-z0-9]*\.localdomain\."` ; do nslookup $i ; done
```
```bash
for j in $(for i in `cat 10.10.in-addr.arpa  | grep -Po " [a-z0-9]*\.localdomain\."` ; do nslookup $i ; done | grep -Po "Address: \K.*") ; do nslookup $j ; done
```

```
named-checkzone localdomain db.localdomain
named-checkzone 10.10.in-addr.arpa. db.10.10

dig 10.10.in-addr.arpa. AXFR
```

```bash
forwarders {
  8.8.8.8;
  8.8.4.4;
};
```

```bash
zone "localdomain" IN {
  type master;
  file "db.localdomain";
};

zone "10.10.in-addr.arpa" IN {
  type master;
  file "db.10.10";
};
```
