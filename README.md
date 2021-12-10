# Ubuntu-Troubleshooting

Restart Network Adapter 

```bash
sudo systemctl restart NetworkManager
```
Enable any system hardware

```bash
xinput list 
xinput enable id_no.
```

sudo: unable to resolve host ubunturohit: Name or service not known

``bash
127.0.0.1 hostname
```

dpkg package repair
```bash
sudo dpkg --configure -a
```

to find port 
```bash
sudo netstat -l | grep sctp
sudo netstat -tplan 38412
```

follow up service 
```bash
sudo journalctl -u magma@magmad -f
```

WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!

```bash
echo''> /home/rohit/.ssh/known_hosts 
```

remove package same name
```bash
sudo rm gateway.*
```

stop services 
```bash
sudo systemctl stop magma@*
```

start service
```bash
sudo systemctl magma@magmad
```
how ip is routing 
```bash
  ip r g 8.8.8.8
  ip r g 192.168.122.17
```




bridgw and virtual network 

```bash
network:
  ethernets:
    enp6s0:
      addresses:
      - 102.222.36.32/25
      - 102.222.36.33/25
      - 102.222.36.34/25
      - 102.222.36.35/25
      - 102.222.36.36/25
      gateway4: 102.222.36.1
      nameservers:
        addresses:
        - 8.8.8.8
        - 8.8.4.4
        search: []
    enp1s0:
      addresses:
      - 192.168.122.11/24
      nameservers:
        addresses:
        - 8.8.8.8
        - 8.8.4.4
        search: []
  version: 2

```
```bash
# This is the network config written by 'subiquity'
network:
  version: 2
  ethernets:
    eno1:
      dhcp4: false
    eno2:
      dhcp4: true
    eno3:
      dhcp4: true
    eno4:
      dhcp4: true

  bridges:
    br0:
      interfaces:
      - eno1
      addresses:
      - 102.222.36.31/25
      gateway4: 102.222.36.1
      nameservers:
        addresses:
        - 8.8.8.8
        - 8.8.4.4

```

