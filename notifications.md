---
title: Notifications
description: 
published: true
date: 2023-07-13T16:03:25.859Z
tags: 
editor: markdown
dateCreated: 2023-07-13T16:03:25.859Z
---

# Notifications
The Notifications feature in AXII allows for seamless integration with existing systems by providing real-time updates on various system events. This enables users to stay informed about the status of their Workflows and Node executions, ensuring efficient communication and collaboration within the team.

## System Events and Callbacks

Various system events, such as the completion of a Workflow or Node execution, can trigger a callback. These callbacks provide real-time updates and help users stay informed about the progress of their work within AXII.

## Supported Callback Types

AXII supports the following types of callbacks:

- **HTTP**: AXII can send notifications as HTTP requests to a specified endpoint, providing a flexible and widely-compatible method for integrating with external systems.
- **GRPC**: For systems that support GRPC, AXII can send notifications as GRPC messages, enabling efficient and high-performance communication between AXII and the target system.

## Notifications API

The Notifications API can be found at the following location: [`impeccableai/proto/events (GitHub)`](https://github.com/impeccableai/proto/tree/main/events). This API provides the necessary information and resources for integrating AXII notifications with your existing systems.

By offering a versatile Notifications feature, AXII ensures that users can easily integrate the platform with their existing infrastructure, providing real-time updates and enhancing overall communication and collaboration.