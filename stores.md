---
title: Stores
description: 
published: true
date: 2023-07-13T16:01:12.649Z
tags: 
editor: markdown
dateCreated: 2023-07-13T16:01:12.649Z
---

# Stores
A Store in AXII is a centralized location where all data is stored, including Data Sources, Tasks' Sources, Artifacts, and more. AXII simplifies the process of accessing and managing data storages, ensuring that users can easily work with their data.

## Data Management

AXII takes care of deduplication and the removal of stale data to save space. These policies are configurable, allowing administrators to control how data is managed and optimize storage usage.

## Required Store

At least one Store is required for AXII to function properly. This ensures that all data has a dedicated and centralized location for storage and management.

## Supported Store Types

AXII supports both FileSystem-like Stores and Object storages such as S3, GCS, and others.

### File System Stores

The basic form of an AXII Store is similar to a Unix FileSystem. It's a PersistentVolumeClaim in a local or remote Cluster, providing a familiar structure for users to work with their data.

### Object Storages (S3, GCS)

AXII also works with Object Storages, providing compatibility with a variety of storage solutions:

- **S3**: Compatible with the S3 API, AXII supports Amazon S3, MinIO, CephFS, and other S3-compatible storage solutions.
- **Google Cloud Storage (GCS)**: AXII supports Google Cloud Storage, allowing users to leverage Google's cloud infrastructure for their data storage needs.

By supporting a variety of storage solutions, AXII provides flexibility for organizations with different infrastructure requirements and preferences.