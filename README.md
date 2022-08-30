# Server NAS and Compute

## Plan
![How_it_looks](https://raw.githubusercontent.com/Jegadit/PrivateServer/master/res/Server%20Prototype%20BPv1.png)


## Part 1:
#### The Server:
Either Proxmox or OpenStack

<b>OpenStack: </b> 
Host os: ubuntu-20.04.3-desktop-amd64 <br/>
RAM alloted: 4GB <br/>
Storage disk space alloted: 25GB <br/>

CMDs:
- sudo -i => get into root mode
- adduser stack
- echo "stack ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers
- checkout [ref](https://www.youtube.com/watch?v=1uyQUU3gXZo&list=PLrDUa_jmF4dFFKl2buxRxWaBDNSeLVJzh&index=5&t=1702s) for network setup
- timedatectl set-timezone Asia/Kolkata
- apt update && apt upgrade -y

- su stack
- cd ~
- git clone https://opendev.org/openstack/devstack -b stable/victoria
- create and write the contents of local.conf in devstack directory
    - set passwords
    - set Host IP
- apt install ntp
- run : ./stack.sh

## Part 2:
#### Deciding the OS instances to be used
- Ubuntu
- Windows
- etc

## Part 3:
#### Setting up a web interface to access the storage to upload and download files using HTTP protocol.
[Miniserve](https://github.com/svenstaro/miniserve) a small, self-contained cross-platform CLI tool that allows to grab the binary and serve some file(s) via HTTP is used.

<b>USES:</b>
- In order to send files to the server to do external processing(heavy lifting work) and to get back the results/output.
- Can be used to upload and retrive media files like a NAS.

```NGROK can be used to access this publicaly from outside the network```

## Part n:
#### Building an image with the source codes and running it:
- docker build -t webapp .
- docker run -d -p 80:5000 --name HiddenLeaf webapp
