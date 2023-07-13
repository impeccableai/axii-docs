---
title: Clusters
description: 
published: true
date: 2023-07-13T16:00:55.481Z
tags: 
editor: markdown
dateCreated: 2023-07-13T16:00:55.481Z
---

# Clusters
AXII simplifies the process of accessing and managing compute clusters, providing a seamless experience for users working with Kubernetes clusters. These clusters are essential for running and scaling workloads efficiently across the organization.

## Compute Clusters

A compute cluster in AXII is simply a Kubernetes cluster. This allows for easy integration with existing Kubernetes-based infrastructure and ensures that users can leverage their existing knowledge and expertise.

## Scheduling Node Execution

AXII schedules the execution of Nodes as Kubernetes jobs in an appropriate cluster. This ensures that workloads are distributed efficiently and can be scaled as needed.

## System Cluster

At least one cluster is required - the default (system) cluster. AXII itself requires a small amount of resources to work properly (approximately 0.5 CPU core and 4GB memory). These numbers grow very slowly with the number of users. The system cluster can also be shared with user workloads, ensuring efficient utilization of resources.

## Max Concurrent Executions

The number of maximum concurrent executions is configurable, allowing administrators to control the workload distribution and resource utilization across the clusters.

## Multiple Compute Clusters

Administrators can add and configure more than one compute cluster. This is useful in situations where teams or data are distributed geographically, ensuring that workloads can be run efficiently across multiple locations.

## Autoscaling

Kubernetes controls the autoscaling behavior of the clusters, ensuring that resources are used efficiently and can be scaled up or down as needed.

## Cloud and On-Premise Support

AXII supports Kubernetes clusters hosted both in the Cloud and on-premise, providing flexibility for organizations with different infrastructure requirements.

## Setting up a Kubernetes Cluster

Setting up a Kubernetes cluster in most Cloud providers is simple and usually takes just a few minutes. This allows organizations to quickly deploy and scale their infrastructure as needed.