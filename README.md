```bash
for i in `cat 10.10.in-addr.arpa  | grep -Po " [a-z0-9]*\.localdomain\."` ; do nslookup $i ; done
```
```bash
for j in $(for i in `cat 10.10.in-addr.arpa  | grep -Po " [a-z0-9]*\.localdomain\."` ; do nslookup $i ; done | grep -Po "Address: \K.*") ; do nslookup $j ; done
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
  file "forward.localdomain";
};

zone "10.10.in-addr.arpa" IN {
  type master;
  file "reverse.localdomain";
};
```
