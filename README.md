# Ubuntu-Troubleshooting
kubernetes auto complete 
```bash
kubectl completion bash > kubecom.sh
source $HOME/.kube/kubecom.sh
```

```bash
kubectl explain pods|less
kubectl explain pods --recursive|less
```

```bash
kubectl  apply -f firstpod.yaml --server-dry-run
kubectl diff -f firstpod.yaml
```
find replace text
```bash
File
sed -i 's/old-text/new-text/g' input.txt

vim 
:%s/emcov2/amcop/g

variable
website=rohit.arora.com
echo $website 
echo ${website:6}
echo ${website:0:5}
echo ${website//rohit/chetali}
```


space
```bash
lsblk
df -h /
du -sh
```
ip a not found 
```bash
apt update
apt install iproute2
```
ping not found
```bash
apt-get update
apt-get install iputils-ping
```
netcat not found
```bash
apt-get install -y netcat
netcat -l -p 8000
```
netstat not found 
```bash
apt-get install net-tools
netstat -nltp
```

wget clone website content 
```bash
download locally links
wget -r -k www.mysysteminfo.com
download at 0 level
wget -r -l 0 mysysteminfo.com

```
compressor 
```bash
folder
tar -cvzf backup.tgz /path/to/source/folder
files
tar -cvzf backup.tgz *

extract
tar -xf backup.tgz

View
tar -ztvf backup.tar.gz

-c : Create a new archive
-v : Verbose output
-f file.tar.gz : Use archive file
-z : Filter the archive through gzip
-j : Filter the archive through bzip2
```
output
```bash
nohup ./prep_baremetal_centos.sh &
```
Find
```bash
find . -type f -name "bin"

find ~/ -type d -name "gtp"

grep -rnw . -e 'developer'

```
tag push docker images
```bash
#!/bin/bash

ECMO_IMAGES=$(docker images | head -n 17 | tail -n 16 | awk '{print $1}')

for i in ${ECMO_IMAGES}
do
  echo "Updatating rohitarora7/${i}"
  docker tag ${i} rohitarora7/${i}
  docker push rohitarora7/${i} 
  docker rmi rohitarora7/${i}
done
```

sudo rights
```bash
sudo usermod -a -G microk8s ubuntu
sudo chown -f -R ubuntu ~/.kube

```

run command with file 
```bash

kubectl create -f - << EOF
#content
EOF
```
download to particular location
```bash
sudo wget url -O /usr/local/bin/rke 
```

sudo writes
```bash
sudo visudo
ubuntu ALL=(ALL) NOPASSWD:ALL
```
forget sudo in vim 
```bash
:w !sudo tee %
```
get all apps installed and grep one
```bash
apt list --installed | grep docker
```
process name from process id
```bash
ps aux | grep 6804
```
uninstall docker 
```bash
 sudo apt remove docker-ce-cli docker-ce-rootless-extras docker-ce
```
do release update 
```bash
do-release-upgrade
```
delete network interface 
```bash
sudo ip link del docker0
```
capture network 
```bash
sudo tcpdump -i eth1
```
Restart Network Adapter 
```bash
sudo systemctl restart NetworkManager
sudo systemctl restart Networking
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
sudo service magma@* stop
sudo service magma@magmad start
```
how ip is routing 
```bash
  ip r g 8.8.8.8
  ip r g 192.168.122.17
```
get details of process id
```bash
ps -p 1671
systemctl restart packagekit
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
default via 102.222.36.1 dev enp6s0 proto static 
102.222.36.0/25 dev enp6s0 proto kernel scope link src 102.222.36.32 
172.17.0.0/16 dev docker0 proto kernel scope link src 172.17.0.1 linkdown 
192.168.122.0/24 dev enp1s0 proto kernel scope link src 192.168.122.11 

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
```bash
default via 102.222.36.1 dev br0 proto static 
102.222.36.0/25 dev br0 proto kernel scope link src 102.222.36.31 
172.17.0.0/16 dev docker0 proto kernel scope link src 172.17.0.1 linkdown 
192.168.122.0/24 dev virbr0 proto kernel scope link src 192.168.122.1 
```
