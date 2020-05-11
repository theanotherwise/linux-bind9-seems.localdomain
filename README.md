#### `named.conf`

```bash
for i in `cat 10.10.in-addr.arpa  | grep -Po " [a-z0-9]*\.localdomain\."` ; do nslookup $i ; done
```


```bash
for j in $(for i in `cat 10.10.in-addr.arpa  | grep -Po " [a-z0-9]*\.localdomain\."` ; do nslookup $i ; done | grep -Po "Address: \K.*") ; do nslookup $j ; done
```

```
options {

  /* ... */

  forwarders {
    8.8.8.8;
    8.8.4.4;
  };
};

zone "localdomain" IN {
  type master;
  file "forward.localdomain";
};

zone "10.10.in-addr.arpa" IN {
  type master;
  file "reverse.localdomain";
};
```

#### `forward.localdomain`
```bash
$TTL    86400
@       IN      SOA     dns0.localdomain. root.localdomain. (
        2011071001      ;       Serial
        3600            ;       Refresh
        1800            ;       Retry
        604800          ;       Expire
        86400           ;       Minimum TTL
)
@       IN      NS      dns0.localdomain.
@       IN      A       10.10.10.10

dns0    IN      A       10.10.10.10

centos7         IN      A       10.10.0.21
centos8         IN      A       10.10.0.22
rhel6           IN      A       10.10.0.30
rhel7           IN      A       10.10.0.31
rhel8           IN      A       10.10.0.32
ol7             IN      A       10.10.0.41
ol8             IN      A       10.10.0.42
debian9         IN      A       10.10.0.51
debian10        IN      A       10.10.0.52
ubuntu16        IN      A       10.10.0.61
ubuntu18        IN      A       10.10.0.62

1sat0           IN      A       10.10.20.10
1sat1           IN      A       10.10.20.11
1sat2           IN      A       10.10.20.12
1sat3           IN      A       10.10.20.13
1sat4           IN      A       10.10.20.14
1sat5           IN      A       10.10.20.15
1sat6           IN      A       10.10.20.16
1sat7           IN      A       10.10.20.17
1sat8           IN      A       10.10.20.18
1sat9           IN      A       10.10.20.19

1vce0           IN      A       10.10.30.10
1vce1           IN      A       10.10.30.11
1vce2           IN      A       10.10.30.12
1vce3           IN      A       10.10.30.13
1vce4           IN      A       10.10.30.14
1vce5           IN      A       10.10.30.15
1vce6           IN      A       10.10.30.16
1vce7           IN      A       10.10.30.17
1vce8           IN      A       10.10.30.18
1vce9           IN      A       10.10.30.19

1esx0           IN      A       10.10.40.10
1esx1           IN      A       10.10.40.11
1esx2           IN      A       10.10.40.12
1esx3           IN      A       10.10.40.13
1esx4           IN      A       10.10.40.14
1esx5           IN      A       10.10.40.15
1esx6           IN      A       10.10.40.16
1esx7           IN      A       10.10.40.17
1esx8           IN      A       10.10.40.18
1esx9           IN      A       10.10.40.19

1zab0           IN      A       10.10.50.10
1zab1           IN      A       10.10.50.11
1zab2           IN      A       10.10.50.12
1zab3           IN      A       10.10.50.13
1zab4           IN      A       10.10.50.14
1zab5           IN      A       10.10.50.15
1zab6           IN      A       10.10.50.16
1zab7           IN      A       10.10.50.17
1zab8           IN      A       10.10.50.18
1zab9           IN      A       10.10.50.19

1pup0           IN      A       10.10.60.10
1pup1           IN      A       10.10.60.11
1pup2           IN      A       10.10.60.12
1pup3           IN      A       10.10.60.13
1pup4           IN      A       10.10.60.14
1pup5           IN      A       10.10.60.15
1pup6           IN      A       10.10.60.16
1pup7           IN      A       10.10.60.17
1pup8           IN      A       10.10.60.18
1pup9           IN      A       10.10.60.19

1for0           IN      A       10.10.70.10
1for1           IN      A       10.10.70.11
1for2           IN      A       10.10.70.12
1for3           IN      A       10.10.70.13
1for4           IN      A       10.10.70.14
1for5           IN      A       10.10.70.15
1for6           IN      A       10.10.70.16
1for7           IN      A       10.10.70.17
1for8           IN      A       10.10.70.18
1for9           IN      A       10.10.70.19

1elk0           IN      A       10.10.80.10
1elk1           IN      A       10.10.80.11
1elk2           IN      A       10.10.80.12
1elk3           IN      A       10.10.80.13
1elk4           IN      A       10.10.80.14
1elk5           IN      A       10.10.80.15
1elk6           IN      A       10.10.80.16
1elk7           IN      A       10.10.80.17
1elk8           IN      A       10.10.80.18
1elk9           IN      A       10.10.80.19

1ans0           IN      A       10.10.90.10
1ans1           IN      A       10.10.90.11
1ans2           IN      A       10.10.90.12
1ans3           IN      A       10.10.90.13
1ans4           IN      A       10.10.90.14
1ans5           IN      A       10.10.90.15
1ans6           IN      A       10.10.90.16
1ans7           IN      A       10.10.90.17
1ans8           IN      A       10.10.90.18
1ans9           IN      A       10.10.90.19

1kst0           IN      A       10.10.100.10
1kst1           IN      A       10.10.100.11
1kst2           IN      A       10.10.100.12
1kst3           IN      A       10.10.100.13
1kst4           IN      A       10.10.100.14
1kst5           IN      A       10.10.100.15
1kst6           IN      A       10.10.100.16
1kst7           IN      A       10.10.100.17
1kst8           IN      A       10.10.100.18
1kst9           IN      A       10.10.100.19

1ora0           IN      A       10.10.110.10
1ora1           IN      A       10.10.110.11
1ora2           IN      A       10.10.110.12
1ora3           IN      A       10.10.110.13
1ora4           IN      A       10.10.110.14
1ora5           IN      A       10.10.110.15
1ora6           IN      A       10.10.110.16
1ora7           IN      A       10.10.110.17
1ora8           IN      A       10.10.110.18
1ora9           IN      A       10.10.110.19

1jen0           IN      A       10.10.120.10
1jen1           IN      A       10.10.120.11
1jen2           IN      A       10.10.120.12
1jen3           IN      A       10.10.120.13
1jen4           IN      A       10.10.120.14
1jen5           IN      A       10.10.120.15
1jen6           IN      A       10.10.120.16
1jen7           IN      A       10.10.120.17
1jen8           IN      A       10.10.120.18
1jen9           IN      A       10.10.120.19

1git0           IN      A       10.10.130.10
1git1           IN      A       10.10.130.11
1git2           IN      A       10.10.130.12
1git3           IN      A       10.10.130.13
1git4           IN      A       10.10.130.14
1git5           IN      A       10.10.130.15
1git6           IN      A       10.10.130.16
1git7           IN      A       10.10.130.17
1git8           IN      A       10.10.130.18
1git9           IN      A       10.10.130.19
```

#### `reverse.localdomain`
```
$TTL    86400
@       IN      SOA     dns0.localdomain. root.localdomain. (
        2011071001      ;       Serial
        3600            ;       Refresh
        1800            ;       Retry
        604800          ;       Expire
        86400           ;       Minimum TTL
)
@       IN      NS      dns0.localdomain.
        IN      A       10.10.10.10

10.10   IN      PTR     dns0.localdomain.

21.0    IN      PTR     centos7.localdomain.
22.0    IN      PTR     centos8.localdomain.
31.0    IN      PTR     rhel7.localdomain.
32.0    IN      PTR     rhel8.localdomain.
41.0    IN      PTR     ol7.localdomain.
42.0    IN      PTR     ol8.localdomain.
51.0    IN      PTR     debian9.localdomain.
52.0    IN      PTR     debian10.localdomain.
61.0    IN      PTR     ubuntu16.localdomain.
62.0    IN      PTR     ubuntu18.localdomain.

10.20   IN      PTR     1sat0.localdomain.
11.20   IN      PTR     1sat1.localdomain.
12.20   IN      PTR     1sat2.localdomain.
13.20   IN      PTR     1sat3.localdomain.
14.20   IN      PTR     1sat4.localdomain.
15.20   IN      PTR     1sat5.localdomain.
16.20   IN      PTR     1sat6.localdomain.
17.20   IN      PTR     1sat7.localdomain.
18.20   IN      PTR     1sat8.localdomain.
19.20   IN      PTR     1sat9.localdomain.

10.30   IN      PTR     1vce0.localdomain.
11.30   IN      PTR     1vce1.localdomain.
12.30   IN      PTR     1vce2.localdomain.
13.30   IN      PTR     1vce3.localdomain.
14.30   IN      PTR     1vce4.localdomain.
15.30   IN      PTR     1vce5.localdomain.
16.30   IN      PTR     1vce6.localdomain.
16.30   IN      PTR     1vce6.localdomain.
17.30   IN      PTR     1vce7.localdomain.
18.30   IN      PTR     1vce8.localdomain.
19.30   IN      PTR     1vce9.localdomain.

10.40   IN      PTR     1esx0.localdomain.
11.40   IN      PTR     1esx1.localdomain.
12.40   IN      PTR     1esx2.localdomain.
13.40   IN      PTR     1esx3.localdomain.
13.40   IN      PTR     1esx3.localdomain.
14.40   IN      PTR     1esx4.localdomain.
15.40   IN      PTR     1esx5.localdomain.
16.40   IN      PTR     1esx6.localdomain.
17.40   IN      PTR     1esx7.localdomain.
18.40   IN      PTR     1esx8.localdomain.
19.40   IN      PTR     1esx9.localdomain.

10.50   IN      PTR     1zab0.localdomain.
11.50   IN      PTR     1zab1.localdomain.
12.50   IN      PTR     1zab2.localdomain.
13.50   IN      PTR     1zab3.localdomain.
14.50   IN      PTR     1zab4.localdomain.
15.50   IN      PTR     1zab5.localdomain.
16.50   IN      PTR     1zab6.localdomain.
17.50   IN      PTR     1zab7.localdomain.
18.50   IN      PTR     1zab8.localdomain.
19.50   IN      PTR     1zab9.localdomain.

10.60   IN      PTR     1pup0.localdomain.
11.60   IN      PTR     1pup1.localdomain.
12.60   IN      PTR     1pup2.localdomain.
13.60   IN      PTR     1pup3.localdomain.
14.60   IN      PTR     1pup4.localdomain.
15.60   IN      PTR     1pup5.localdomain.
16.60   IN      PTR     1pup6.localdomain.
17.60   IN      PTR     1pup7.localdomain.
18.60   IN      PTR     1pup8.localdomain.
19.60   IN      PTR     1pup9.localdomain.

10.70   IN      PTR     1for0.localdomain.
11.70   IN      PTR     1for1.localdomain.
12.70   IN      PTR     1for2.localdomain.
13.70   IN      PTR     1for3.localdomain.
14.70   IN      PTR     1for4.localdomain.
15.70   IN      PTR     1for5.localdomain.
16.70   IN      PTR     1for6.localdomain.
17.70   IN      PTR     1for7.localdomain.
18.70   IN      PTR     1for8.localdomain.
19.70   IN      PTR     1for9.localdomain.

10.80   IN      PTR     1elk0.localdomain.
11.80   IN      PTR     1elk1.localdomain.
12.80   IN      PTR     1elk2.localdomain.
13.80   IN      PTR     1elk3.localdomain.
14.80   IN      PTR     1elk4.localdomain.
15.80   IN      PTR     1elk5.localdomain.
16.80   IN      PTR     1elk6.localdomain.
17.80   IN      PTR     1elk7.localdomain.
18.80   IN      PTR     1elk8.localdomain.
19.80   IN      PTR     1elk9.localdomain.

10.90   IN      PTR     1ans0.localdomain.
11.90   IN      PTR     1ans1.localdomain.
12.90   IN      PTR     1ans2.localdomain.
13.90   IN      PTR     1ans3.localdomain.
14.90   IN      PTR     1ans4.localdomain.
15.90   IN      PTR     1ans5.localdomain.
16.90   IN      PTR     1ans6.localdomain.
17.90   IN      PTR     1ans7.localdomain.
18.90   IN      PTR     1ans8.localdomain.
19.90   IN      PTR     1ans9.localdomain.

10.100  IN      PTR     1kst0.localdomain.
11.100  IN      PTR     1kst1.localdomain.
12.100  IN      PTR     1kst2.localdomain.
13.100  IN      PTR     1kst3.localdomain.
14.100  IN      PTR     1kst4.localdomain.
15.100  IN      PTR     1kst5.localdomain.
16.100  IN      PTR     1kst6.localdomain.
17.100  IN      PTR     1kst7.localdomain.
18.100  IN      PTR     1kst8.localdomain.
19.100  IN      PTR     1kst9.localdomain.

10.110  IN      PTR     1ora0.localdomain.
11.110  IN      PTR     1ora1.localdomain.
12.110  IN      PTR     1ora2.localdomain.
13.110  IN      PTR     1ora3.localdomain.
14.110  IN      PTR     1ora4.localdomain.
15.110  IN      PTR     1ora5.localdomain.
16.110  IN      PTR     1ora6.localdomain.
17.110  IN      PTR     1ora7.localdomain.
18.110  IN      PTR     1ora8.localdomain.
19.110  IN      PTR     1ora9.localdomain.

10.120  IN      PTR     1jen0.localdomain.
11.120  IN      PTR     1jen1.localdomain.
12.120  IN      PTR     1jen2.localdomain.
13.120  IN      PTR     1jen3.localdomain.
14.120  IN      PTR     1jen4.localdomain.
15.120  IN      PTR     1jen5.localdomain.
16.120  IN      PTR     1jen6.localdomain.
17.120  IN      PTR     1jen7.localdomain.
18.120  IN      PTR     1jen8.localdomain.
19.120  IN      PTR     1jen9.localdomain.

10.130  IN      PTR     1git0.localdomain.
11.130  IN      PTR     1git1.localdomain.
12.130  IN      PTR     1git2.localdomain.
13.130  IN      PTR     1git3.localdomain.
14.130  IN      PTR     1git4.localdomain.
15.130  IN      PTR     1git5.localdomain.
16.130  IN      PTR     1git6.localdomain.
17.130  IN      PTR     1git7.localdomain.
18.130  IN      PTR     1git8.localdomain.
19.130  IN      PTR     1git9.localdomain.
```
