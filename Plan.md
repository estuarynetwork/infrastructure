# Network Plan

## Goals

* Coastal Resiliency via:
    * High Availability and load balancing between hosts
    * Sharing of encrypted backups between hosts
    * Connection to overlay mesh network

## Docker Swarm vs Kubernetes

The network will use docker swarm for the reasons listed [here](https://hackernoon.com/kubernetes-vs-docker-swarm-a-comprehensive-comparison-73058543771e)

## Nodes 

| Node Name | IP Address | Type | `docker` version | `docker-compose` version | `docker-machine` version | Notes |
| ----- | ----- | ----- | ---- | ---- | ---- | ---- |
| mycelium (laptop) | Transient | Worker | x | x | x | x | x |
| wheelhouse | 7X.XX.XX.X79 | Manager | docker version 18.09.7, build 2d0083d | docker-compose version 1.24.1, build 4667896b | n/a |
| roost | 7X.XX.XX.X29 | Manager | Docker version 19.03.5, build 633a0ea | docker-compose version 1.24.1, build 4667896b | docker-machine version 0.16.2, build bd45ab13 |

### Necessary Ports to Open

| Port | Protocol | Reason |
| --- | --- | ---- |
| 2377 | TCP | Docker Swarm cluster management communications |
| 7946 | TCP + UDP | Docker Swarm communication among nodes |
| 4789 | UDP | Docker Swarm |overlay network traffic
| 50 | IP | Docker Swarm ESP Traffic for encrypted overlay network | 

## Risks

| Risk | Likelihood | Impact | Mitigation |
| ---- | ---- | ---- | ---- |
| Power Outage | TODO | TODO | Failover |
| Security | TODO | TODO | TBD (break out into multiple subrisks) |
