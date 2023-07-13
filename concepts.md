---
title: Concepts
description: This page explains the most basic AXII concepts.
published: true
date: 2023-07-13T16:40:54.181Z
tags: 
editor: markdown
dateCreated: 2023-07-05T14:45:51.836Z
---

# Concepts
To better understand the AXII platform, it is important to familiarize yourself with some key concepts. These concepts form the foundation of the platform's functionality and user interactions.

## Data Source

A Data Source is a static, immutable piece of data, such as a sequence of bytes that can be interpreted as a (structured) text file, images, videos, etc. Users can easily bring their existing data to AXII, as the platform supports multiple ways of doing so. Internally, a Data Source is linked to an inventory object, which is stored in one or more Stores.

> **Example:** A CSV file with the Iris dataset.
{.is-success}

> **Not a Data Source:** A database, because it is not immutable. However, data can be fetched from a database to create a Data Source.
{.is-warning}

## Task

A Task is anything that is executed on the platform. Conceptually, it is closest to a container. Users can easily create new Tasks using their favorite frameworks and existing source code without any modifications. Tasks can consume inputs, generate outputs, and accept parameters. They may be plain containers or more complex structures like Python scripts or Spark jobs.

> **Example:** A Python script that trains a machine learning model.
{.is-success}

## Workflow

A Workflow is a set of nodes and edges describing a directed acyclic graph (DAG). Nodes represent either a Data Source, a Task, an Action, or another Workflow (sub-workflow). Edges describe how data and artifacts flow between nodes. Workflows are immutable and can also have a name and version for convenience.

## Draft

Users most often interact with the AXII platform by creating and editing Drafts. A Draft is an editable Workflow, providing a flexible way to design and adjust Workflows before submitting them for execution.

## Experiment

An Experiment is an execution of a Workflow.