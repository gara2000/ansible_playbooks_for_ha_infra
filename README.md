# This is the infra server
it will operate as a workstation, to provision the other servers

## Hosts
* host: the machine running all the other virtual machines
* infra1: the workstation running all of the ansible playbooks and the DNS server
* node1, node2: hosts running the applications
* sotrage: host running the storage services

## Network
All the machines are configured with a host-only adabter that has the 192.168.56.0/24 subnetwork

## DNS
The infra1 server has the role of the DNS server, it is responsible for resolving the addresses in the "robust.net" domain.

It resolves the following addresses:
* host.robust.net	@	 192.168.56.1
* registry.robust.net	@	 192.168.56.1
* infra1.robust.net 	@	 192.168.56.2
* node1.robust.net	@	 192.168.56.3
* node2.robust.net	@	 192.168.56.4
* storage.robust.net	@	 192.168.56.5

> the .robust.net prefix can be removed in communications inside the domain

## Registry
The host runs a registry server as a docker container, inside of which the different applications code will be stored
* the registry is at **registry.robust.net**
