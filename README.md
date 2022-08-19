# Server NAS and Compute

## Plan
![How_it_looks](https://raw.githubusercontent.com/Jegadit/PrivateServer/master/res/Server%20Prototype%20BP.png)


## Part 1:
#### The Server:
Either Proxmox or OpenStack

<b>OpenStack: </b> 

- needed: local.config

## Part 2:
#### Building an image with the source codes and running it:
- docker build -t webapp .
- docker run -d -p 80:5000 --name Cloud_OS webapp
