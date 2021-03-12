---
title: Size Your TiDB Cluster
summary: Learn how to select the number of nodes for your TiDB cluster.
---

# Size Your TiDB Cluster

This document describes how to select the number of nodes for your TiDB cluster.

## Size TiDB

TiDB is for computing only and does not store data. It is horizontally scalable. Each TiDB Cloud cluster requires at least two TiDB nodes.

## Size TiKV

TiKV is responsible for storing data. It is horizontally scalable and the number of nodes should be **at least 1 set (3 nodes in 3 different Available Zones)**.

Data in each TiDB Cloud cluster has 3 replicas, and each replica is distributed in a different availability zone.

> **Note:**
>
> When you scale your TiDB cluster, nodes in the 3 availability zones are increased or decreased at the same time. For how to scale in or scale out a TiDB cluster based on your needs, see [Scale Your TiDB Cluster](scale-tidb-cluter.md).

For example:

Supposing the size of your MySQL dump files is 5 TB and the TiDB compression ratio is 70%, the storage needed is 3584 GB.

If you choose the **t1.standard** tier on AWS and each TiKV node has 1900 GB storage, then the required number of TiKV nodes are as follows:

- Minimum number of TiKV nodes:  `3584 ÷ 1900 × 3 (replica) ≈ 6`

## Size TiFlash

TiFlash synchronizes data from TiKV in real time and supports real-time analytics workloads right out of the box, It is horizontally scalable. You can specify TiFlash nodes if you choose **H1.standard** tier.

The minimun number of TiFlash depends on the TiFlash replica counts for specific tables.

- Minimun number of TiFlash nodes: `min((compressed size of table A * replicas for table A + compressed size of table B * replicas for table B) / size of each TiFlash capacity, max(replicsa for table A, replicas for table B))`

For example, if you choose the **H1.standard** tier on AWS whose TiFlash node has 1900 GB storage, you set 2 replicas for table A (compressed size is 800GB) and 1 replica for table B (compressed size is 100GB). Then the TiFlash nodes are as follows:

- Minimun number of TiFlash nodes: `min((800GB * 2 + 100GB * 1) / 1900GB, max(2, 1)) ≈ 2`
