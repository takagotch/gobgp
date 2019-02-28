### gobgp
---
https://github.com/osrg/gobgp

```
[global.config]
  as = 64512
  router-id = "192.168.255.1"
  
[[neighbors]]
  [neighbors.config]
    neighbor-address = "10.0.255.1"
    peer-as = 65001
    
[[neighbors]]
  [neighbors.config]
    neighbor-address = "10.0.255.2"
    peer-as = 65002
  
```

```
sudo -E gobpd -f gobpd.conf

sudo -E gobgpd -t yaml -f gobgpd.yml
gobgp neighbor 10.0.255.1
gobgp global rib
gobgp neighbor 10.0.255.1 adj-in
gobgp neigbor 10.0.255.1 adj-out
```

```
global:
  config:
    as: 64512
    router-id: 192.168.255.1
neighbors:
  - config:
    neighbor-address: 10.0.255.1
    peer-as: 65001
  - config:
    neighbor-address: 10.0.255.2
    peer-as: 65002
```


