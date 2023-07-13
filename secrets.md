---
title: Secrets
description: 
published: true
date: 2023-07-13T16:00:38.161Z
tags: 
editor: markdown
dateCreated: 2023-07-13T16:00:38.161Z
---

# Secrets
AXII simplifies the management and sharing of secrets in a secure manner across your organization. Secrets are essential for providing access to restricted resources, APIs, and other sensitive data, while ensuring that the information remains secure.

## Managing Secrets

Administrators have the ability to create, edit, and remove secrets through the Secrets page in the System Config section of AXII. This provides a centralized location for managing secrets and helps maintain security throughout the organization.

## Structure of Secrets

A secret in AXII is almost identical to a Kubernetes' Secret. Each secret has a unique name and one or more key-value pairs associated with it. This structure allows for easy integration with Kubernetes-based infrastructure.

## Access Control

Once a secret is created, users typically do not have direct access to its values. This ensures that sensitive information remains secure and can only be accessed by authorized personnel or processes during runtime.

## Storage and Security

To enhance security, secrets are stored directly in the Clusters store, using Kubernetes' Secrets API. This means that secrets are not stored in AXII's internal database, reducing the risk of unauthorized access or data breaches.

## Synchronization Across Clusters

Secrets are automatically synced across all Clusters within the AXII platform. This ensures that the most up-to-date and accurate secrets are available for use throughout the organization, regardless of the Cluster in which they are being used.