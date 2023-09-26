---
title: Workflows and Drafts
description: 
published: true
date: 2023-09-26T13:24:35.571Z
tags: 
editor: markdown
dateCreated: 2023-07-13T13:47:58.935Z
---

# Workflows and Drafts
## Introduction

Workflows and Drafts are very similar concepts in AXII.

### Workflow

A Workflow is a set of Nodes and Edges that describe a directed acyclic graph (DAG). Nodes represent either a data source, a task, an action, or another workflow (sub-workflow). Edges describe how the data and artifacts flow between nodes. Workflows are immutable and can also have a name and a version for convenience.

### Draft

A Draft is a Workflow in a \"work-in-progress\" stage. Users most often interact with the application by creating and editing drafts.

Watch demo video (https://youtu.be/T_lUkybwma8):
[![Composing a Draft in AXII](http://img.youtube.com/vi/T_lUkybwma8/0.jpg)](http://www.youtube.com/watch?v=T_lUkybwma8 "Composing a Draft in AXII")

## Deep Dive

### Nodes and Edges
Nodes in a Workflow can contain:

- Task
- DataSource
- Action
- Sub-Workflow

Nodes have Inputs, Outputs, and Parameters that reflect the Task's interface. They are pre-filled with default values and can be overwritten.

Edges describe how the data flows between Nodes.

### Workflow Parameters
A Workflow can have Parameters, which are global constants for every Node in the Workflow. These parameters can contain Macros. For more information on using Macros, refer to the [Macros documentation page](/macros).

Values in a Node can use Macros to reference Workflow Parameters.

### Runtime Environment
Users can specify a Runtime Environment for the entire Workflow as well as individual Nodes.

## Examples

Publicly available repository with Workflows created by us: [impeccableai/axii-examples (github.com)](https://github.com/impeccableai/axii-examples)

Workflows can be imported using AXII's Import feature.

By understanding the concepts of Workflows and Drafts, users can effectively design, develop, and execute AI workflows in AXII. This allows AI experts to focus on their work while the platform handles the underlying infrastructure and resource management.