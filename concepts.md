---
title: Concepts
description: This page explains the most basic AXII concepts.
published: true
date: 2023-07-05T14:46:45.650Z
tags: 
editor: markdown
dateCreated: 2023-07-05T14:45:51.836Z
---

# Concepts

In this section, we discuss the key concepts that are essential to understanding the AXII AI Development Platform. These concepts include Data Source, Task, Workflow, Draft, and Experiment. We will explain each concept and provide examples to help you gain a better understanding of how they work together in the platform.

## Data Source

A **Data Source** is a static, immutable piece of data. It is simply a sequence of bytes that can be interpreted as various types of data, such as structured text files, images, videos, etc. Each Data Source is internally linked to an inventory object which is stored in one or more storages.

**Example:** A CSV file containing the Iris dataset.

It's important to note that a database is **not** considered a Data Source, as it is not immutable. However, data can be fetched from a database to create a Data Source using a Task.

## Task

A **Task** is anything that is executed within the platform. Conceptually, it is closest to a container. Tasks can:

- Consume some inputs
- Generate some outputs
- Take some parameters

Tasks may be as simple as a plain container, or more complex, such as a Python script or a Spark job.

**Example:** A Python script that trains a machine learning model.

## Workflow

A **Workflow** is a set of nodes and edges describing a directed acyclic graph (DAG). Nodes within a Workflow represent either a Data Source, a Task, an Action, or another Workflow (sub-workflow). Edges describe how the data and artifacts flow between nodes. Workflows are immutable and can have a name and a version for convenience.

## Draft

A **Draft** is how users most often interact with the AXII application, by creating and editing drafts. A Draft is an editable Workflow, allowing users to experiment and modify their work before finalizing it.

## Experiment

An **Experiment** is an execution of a Workflow. Once a Workflow has been executed, it becomes an Experiment, which is immutable. This means that the state of the Workflow during the Experiment cannot be changed.

In summary, the AXII AI Development Platform utilizes Data Sources, Tasks, Workflows, Drafts, and Experiments to enable users to create, test, and execute their AI projects. Understanding these key concepts is crucial for effectively using the platform and maximizing its potential.