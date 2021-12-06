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

