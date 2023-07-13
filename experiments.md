---
title: Experiments
description: 
published: true
date: 2023-07-13T12:29:23.297Z
tags: 
editor: markdown
dateCreated: 2023-07-13T12:12:59.089Z
---

# Experiments
## Introduction

An Experiment in AXII is an execution of a workflow. It is immutable, meaning that once it has been submitted, it cannot be changed. This is important for maintaining the integrity and consistency of the results produced by the Experiment.

## Deep Dive

### Execution

After an Experiment is submitted, AXII's Orchestrator takes over and executes the Workflow. Each Node within the Workflow goes through multiple stages during the execution, which are described below. The state of the whole Experiment is a derivative of its Nodes' statuses. Internally, a Node is translated to a Kubernetes' Job, ensuring reliable and scalable execution.

#### Node States

```mermaid
%%{
  init: {
    'theme': 'base',
    'themeVariables': {}
  }
}%%
flowchart LR
 		SUBMITTED([SUBMITTED]):::submitted --> PREPARING([PREPARING]):::preparing --> QUEUEING([QUEUEING]):::queueing --> RUNNING([RUNNING]):::running --> FINALIZING([FINALIZING]):::finalizing --> DONE([DONE]):::done
    FINALIZING --> FAILED([FAILED]):::failed
    RUNNING --> FAILED
    QUEUEING --> FAILED
    PREPARING --> FAILED
    FINALIZING --> CANCELED([CANCELED]):::canceled
    RUNNING --> CANCELED
    QUEUEING --> CANCELED
    PREPARING --> CANCELED
    SUBMITTED --> CANCELED
    PREPARING -----> ALREADY_DONE([ALREADY_DONE]):::alreadyDone
    classDef submitted fill:#FFC107,color:#fff;
    classDef queueing fill:#673AB7,color:#fff;
    classDef preparing fill:#3F51B5,color:#fff;
    classDef running fill:#2196F3,color:#fff;
    classDef finalizing fill:#009688,color:#fff;
    classDef done fill:#4CAF50,color:#fff;
    classDef alreadyDone fill:#8BC34A,color:#fff;
    classDef canceled fill:#607D8B,color:#fff;
    classDef failed fill:#b71c1c,color:#fff;
```

This chart illustrates the different states that a Node can transition through during the execution of an Experiment.

#### Experiment States

```mermaid
%%{
  init: {
    'theme': 'base',
    'themeVariables': {}
  }
}%%
flowchart LR
 		SUBMITTED([SUBMITTED]):::submitted --> RUNNING([RUNNING]):::running --> DONE([DONE]):::done
    SUBMITTED --> CANCELLED([CANCELLED]):::canceled
    RUNNING --> FAILED([FAILED]):::failed
    RUNNING --> CANCELLED
    classDef submitted fill:#FFC107,color:#fff;
    classDef running fill:#2196F3,color:#fff;
    classDef done fill:#4CAF50,color:#fff;
    classDef canceled fill:#607D8B,color:#fff;
    classDef failed fill:#b71c1c,color:#fff;
```

This chart shows the possible states of an Experiment, which are determined by the statuses of its Nodes.

### Artifacts Cache

AXII takes care of optimizing the execution and avoiding redundant, repeated computation. It does this by maintaining an Artifacts Cache. When looking for a cache entry, AXII takes into account various factors, such as the Node's Task, whether the Task is deterministic or not, the Node's inputs, parameters, and Runtime.

If a valid cached Artifact is found, AXII skips the execution of the Node and sets its state to `ALREADY DONE`. This significantly improves the efficiency of the Experiment execution.

### Autoscaling & Queueing

Depending on the configuration, AXII can scale compute resources to match the current demand and/or use queueing. This ensures that the platform can handle varying workloads and efficiently distribute resources among different Experiments.

### Recurring Experiments

AXII supports scheduling Experiments, which is useful for executing Experiments based on time intervals. This feature, together with Macros, allows users to create dynamic Workflows to, for example, fetch and process daily data for later use in model training Workflows. This makes it easy for users to keep their models up-to-date with the latest data and trends.