# Consul on Hypriot

This repo contains some configs and scripts to quickly setup consul nodes on a raspberry running hypriot.
If there is a local docker you can also run a registrator container connected to the consul node.

---
## How to use

From project root do following

```bash
./bin/install-node <first|follow|webui|registrator>
```
Basically this will deploy the consul binary and a systemd unit.


I use the laziest approach to bootstrap a consul cluster. With "install-node first" i create a one node cluster.
On every following machine i simply use "install-node follow" and pass the address of my first node.
Nodes installed with follow will simply join the cluster by ip


##### consul-first.service
This will start a consul node in server mode with bootstrap-expect set to 1.
Once started you have a working consul cluster with one node

##### consul.service
This will start a consul node in server mode joining the node i specified during install. The join address is hardcodet in the systemd unit.

#### consul-webui.service
This will start a following node with the addition of providing a webui

---

## Why you should not use it
This is not really made to be used by people other than me. You can do better than this.
Also the consul binary wont be updated
