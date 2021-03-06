---
description: This page describes possible congestion issues in the WekaIO system.
---

# System Congestion

## Overview

The WekaIO system is built to be very efficient, provide maximum performance and saturate the network links.

In some situations, the system itself may slow down IOs when reaching some limits \(or even block new IOs at higher limits\) until the congested resource is relieved. Such situations may be transient and the issue will be resolved on its own after a short time. However, there are also cases that suggest an issue that needs to be addressed, such as a workload maxing out the resources of the cluster. In such cases, the cluster resources must be expanded, as described in [Expanding & Shrinking Cluster Resources](expanding-and-shrinking-cluster-resources/). Contact the WekaIO Support Team for more information on this.

## System Congestion Events/Alerts

The WekaIO system can issue several types of congestion events/alerts:

| Type | Description | Actions |
| :--- | :--- | :--- |
| FIBERS | Extreme load of concurrent system operations on a node | This is usually a transient situation due to load on them system. If the load is consistent and the problem persists, add more resources \(hosts/cores\), as described in [Adding a Backend Host](expanding-and-shrinking-cluster-resources/stages-in-adding-a-backend-host.md) or [Addition of CPU cores](expanding-and-shrinking-cluster-resources/expansion-of-specific-resources.md#addition-of-only-cpu-cores). |
| DESTAGER | Too many pending IOs are waiting to be written for a specific node | This is usually a transient situation due to load on them system. If the load is consistent and the problem persists, add more hosts to the cluster as described in [Adding a Backend Host](expanding-and-shrinking-cluster-resources/stages-in-adding-a-backend-host.md), or expand the host resources as described in [Expansion of Specific Resources](expanding-and-shrinking-cluster-resources/expansion-of-specific-resources.md). |
| SSD | Too many pending IOs to the SSD | If there is a single SSD, it is probably faulty and needs to be replaced. If there are multiple SSDs, the load on the system is too high. To handle such a load, more SSDs should be added to the system, as described in [Expansion of Specific Resources](expanding-and-shrinking-cluster-resources/expansion-of-specific-resources.md#addition-of-memory-and-network-interface). |
| RAID\_NOT\_OK | More IO failures than can be handled have occurred, and IOs cannot be served | Make sure to bring up any host that might be down. If all hosts are up, contact the WekaIO Support Team. |
| XDESTAGE | Auxiliary cluster resources are low | This is usually a transient situation due to load on the system. If the load is consistent and the problem persists, add more hosts to the cluster as described in [Adding a Backend Host](expanding-and-shrinking-cluster-resources/stages-in-adding-a-backend-host.md), or consult the WekaIO Support Team. |

