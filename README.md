# Consul on Hypriot

This repo contains some configs and scripts to quickly setup consul nodes on a raspberry running hypriot.

---
## How to use

From project root do following

```bash
./bin/install-node <server|agent>
```

This will deploy the consul binary, configs and respective systemd unit.

##### consul-server.service
This will start a consul node in server mode with bootstrap-expect set to 1.
Once started you have a working consul cluster with one node

##### consul-agent.service
This will start a consul node in agent mode joining the node you specified during install.

---
## Why you should not use it

- A consul cluster should have 3 to 5 nodes in server mode
- The binary wont be up to date
- You can make a better systemd unit
