---
title: Tasks
description: 
published: true
date: 2023-07-13T13:37:46.900Z
tags: 
editor: markdown
dateCreated: 2023-07-13T13:37:46.900Z
---

# Tasks
## Introduction

A Task in AXII represents anything that is executed, and conceptually, it is closest to a container. Tasks can consume inputs, generate outputs, and take parameters. They can range from simple containers to more complex entities, such as Python scripts or Spark jobs. An example of a Task is a Python script that trains a machine learning model.

## Deep Dive

### Immutability

With some minor exceptions, Tasks are immutable.

### Interface

#### Inputs and Outputs

Inputs are the data that a Task consumes (processes) and are read-only. Outputs, on the other hand, are the data that a Task generates and are read-write. These outputs are called Artifacts. Both inputs and outputs are named and have a Kind (required) and Type Hint (optional). They are marked as semi-circles on the left and right side of a Task's block.

#### Parameters

Parameters typically control a Task's execution. All three components (inputs, outputs, and parameters) are passed as command-line arguments to the container.

### Determinism

Tasks can be marked as \"Nondeterministic,\" which enforces Task execution in situations where its results would normally be loaded from Artifacts cache. While this feature is useful in some specific cases, in most situations, it is recommended to use a Task's parameter (e.g., RandomSeed) to set the RNG explicitly.

### Runtimes

Various runtime types are supported for Tasks:

1. **Container**: The simplest runtime type.
2. **Python**: Based on a container, this Task also has source code that is executed.
3. **Spark Job**: Spark Jobs are executed by the Spark Operator in a configured Spark Cluster.
4. **SQL**: A utility type that executes SQL queries. DB connection parameters are read from environment variables. The most convenient way to configure the connection is to use a ConfigSet. The source is preprocessed with Macro Engine before execution, allowing users to write SQL templates that are instantiated when the Task is submitted for execution.

### Source

A Task's Source can be either a file or a directory. The Source can be created or edited using a built-in code editor, uploaded from a local machine, or fetched from a public or private Git Repository. Tasks can also \"Follow\" a specified reference from a Git repo and pull the newest version before each execution.

### Task State

Tasks can be in one of three states:

1. **Active**: The standard state.
2. **Deprecated**: The Task can still be executed, but using a newer version is desired.
3. **Disabled**: The Task can no longer be executed.

### Examples

Publicly available repository with Tasks created by us: [impeccableai/axii-examples (github.com)](https://github.com/impeccableai/axii-examples)

Tasks can be imported using AXII's Import feature.

### Task on a Workflow

A Node with a Task has Inputs and Outputs that reflect the Task's interface. The Node also has Parameters that reflect the Task's interface and use the Task's default values. Task's Parameters and Runtime can usually be overwritten with Node's values.

Understanding the various aspects of Tasks in AXII allows users to effectively develop and execute AI workflows. The flexibility provided by AXII ensures that AI experts can focus on their work while the platform takes care of the underlying infrastructure and resource management.