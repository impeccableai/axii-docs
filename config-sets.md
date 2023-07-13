---
title: Config Sets
description: 
published: true
date: 2023-07-13T16:03:42.907Z
tags: 
editor: markdown
dateCreated: 2023-07-13T16:03:42.907Z
---

# Config Sets
Config Sets in AXII provide a convenient way to manage Environment variables and Secrets, simplifying the process of using these values in a consistent and secure manner. They help users easily configure access to restricted resources, APIs, and other sensitive information.

## Key-Value Pairs

A Config Set is a list of key-value pairs, where values can be raw strings or references to defined Secrets. This allows users to securely store sensitive information and easily reference it within their Nodes.

## Use Cases

Config Sets can be used to simplify the configuration of access to various resources, such as third-party APIs, cloud storage services, or other restricted resources. For example, a Config Set with two values (the ID and secret key for Amazon's S3) can be used to configure access to an S3 bucket.

## Attaching Config Sets to Nodes

Config Sets can be attached to a Node before submitting it for execution. This ensures that the Node has access to the necessary Environment variables and Secrets, enabling secure and efficient access to restricted resources during the execution.

By offering Config Sets, AXII provides an easy-to-use method for managing Environment variables and Secrets, allowing users to securely configure access to sensitive resources and ensuring consistent configuration across their Nodes.