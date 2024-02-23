# Ubuntu-Troubleshooting
rg search
```
apt-get install ripgrep
```
Encrypt files
```
zip --encrypt file.zip files
```
apk list to remove
```
cd /var/lib/apt/lists/
```
latest file
```
ls -lrth
```
sha
```
sha256sum filename.pdf
```
package
```
dpkg --listfiles bashtor
```
bash
```
sudo dpkg --configure -a
```

gcc g++ 

```bash
sudo apt-get install build-essential manpages-dev
```


Process kill
```bash
pidof slack
sudo kill -9 process_id
sudo kill -9 `pidof programe_name`
killall program_name
```

Find pid from port number
```bash
sudo ss -lptn 'sport = :80'
```

Limit Resourse
```bash
ulimit -Sa
ulimit -n 5
```

SSL Information
```bash
echo | openssl s_client -servername yourdomain.com -connect yourdomain.com:443
```

system link 
```bash
sudo ln -s /usr/bin/python3 /usr/bin/python
```

software installed info 
```bash
apt-cache show python-is-python3
```

python fix
```bash
sudo apt update
sudo apt install python-is-python3
```

youtube download 
```bash
pip insyall youtube-dl

or

sudo wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl

sudo chmod a+rx /usr/local/bin/youtube-dl

hash -r

 youtube-dl -f best -citw -v playlist url
```

ss
```bash
ss -tl4pn
ss -tn src :22
ss -tn dst :22
ss -an | grep :22


```

See the ENV
```bash
env
export PYTHONPATH=/opt/liboqs-python
cat /etc/profile
cat ~/.profile
cat ~/.bashrc
```

change owership of folder to current user 
```bash
chown -R $USER:$USER /opt
```

Indian server hit
```bash
cd /etc/apt/
sed 's/in.archive/archive/g' sources.list
sed -i 's/in.archive/archive/g' sources.list
```

keep server live
```bash
cd /directory/where/html/is/present
python -m SimpleHTTPServer 8000  # For python 2
python3 -m http.server 8000 # For python 3
```

watch
```bash
watch -n 0.1 ls -lh ubuntu-20.04.4-live-server-amd64.iso
```

system details
```bash
 sudo lshw
 lsusb
 lscpu
 lspci
 lsscsi
 xinput
 lsblk
 cat /etc/*-release
```

Time
```bash
timedatectl status
timedatectl list-timezones | grep -i kol
timedatectl set-timezone Asia/Kolkata
```

ssh  
```bash
 sudo apt install openssh-server
 sudo service ssh status
 sudo service ssh start
 sudo service ssh restart
 sudo netstat -ltnp | grep sshd
 sudo ufw allow port /tcp
 sudo ufw allow 2244/tcp
 sudo ufw reload
 sudo ufw status
 
 ssh test.server.com
 ssh-keygen
 ssh-copy-id ubuntu@192.168.5.5
 echo 'ls' | ssh ubuntu@192.168.5.171

 
```


Data filter
```bash
kubectl get pods --no-headers | awk '{print $3}'
kubectl get pods | tail -n +2 | awk '{print $3}'

kubectl get pods calico-node-wx8kq -o jsonpath={.status.phase}
kubectl get pods -o jsonpath={.status.phase};echo
kubectl get pods calico-node-wx8kq -o json | jq '.status.phase'
kubectl get pods calico-node-wx8kq -o json | jq -r '.status.phase'

```

```bash
scp ./codebook_1.0.0_amd64.deb ubuntu@192.168.122.165:~ 
scp ubuntu@192.168.122.3:codebook_1.0.0_amd64.deb ~/.kube/ 
scp ubuntu@192.168.122.3:~/.kube/config ~/.kube/config_microk8s
scp mint@192.168.0.40:"/home/mint/Downloads/RESUME\ 2022\ ROHIT\ ARORA.pdf" .
```

find replace text
```bash
File
sed -i 's/old-text/new-text/g' input.txt

find . -name \*.h -exec sed -i 's,<oqs/,",g' {} \;
find . -name \*.h -exec sed -i "s/<oqs/<oqss/g" {} \;

sed 's+http://+https://www.cyberciti.biz+g' input.txt

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
