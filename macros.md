---
title: Macros
description: 
published: true
date: 2023-07-13T13:43:03.493Z
tags: 
editor: markdown
dateCreated: 2023-07-13T13:42:07.604Z
---

# Macros

The Macro Engine in AXII allows users to specify dynamic values or reference global parameters. Most values can be specified using Macros. Macros are evaluated when the Experiment is submitted for execution, ensuring that all macros in an Experiment are evaluated at the same time before starting the execution. This prevents unexpected behavior, such as a changed date in the middle of an Experiment's execution.

## Usage

Macro expressions are contained in double curly brackets (e.g., `{{ macro }}`). Expressions in a macro can reference another known constant, variable, or function (e.g., `{{ param + 1 }}`) as long as they don't create a cycle.

## Evaluation

The macro language is statically typed with inferred types. Macros in Workflow's parameters are evaluated in an environment with a defined constant `experiment_uuid`. Macros in Node's parameters are evaluated in an environment with a defined `experiment_uuid` and Workflow's parameters.

## Reference

### Builtin constants

- `HOUR: duration`
- `DAY: duration`
- `WEEK: duration`

### Builtin functions

- Type casting functions: `int`, `float`, `string`
- `random: () -> float`
  - Example: `random() = 0.2137`
- `random_int: () -> int`
  - Example: `random() = 2137`
- `random_intn: (max: int) -> int`
  - Example: `random_intn(10) = 5`
- `random_uuid: (strip_dashes: bool? = False) -> str`
  - Example: `random_uuid() = "41d49816-523c-2137-afee-59c7c2d9825a"`
- `now: () -> time`
  - Example: `now() `= time object representing the current time
- `date: () -> time`
  - Example: `date(2005, 4, 2)` = time object representing the date 2005-04-02
- `time_add: (time, duration) -> time`
  - Example: `time_add(now(), -DAY)` = time object representing the exact same time yesterday
- `strptime: (string, string) -> time`
  - Example: `strftime(date(2005, 04, 02, 21, 37, 00), "%Y-%m-%d %H:%M:%S")` = time object representing the date 2005-04-02 21:37:00
- `strftime: (time, string) -> string`
  - Example: `strftime(date(2005, 04, 02, 21, 37, 00), "%Y-%m-%d") = "2004-04-02"`

By understanding how to use macros in AXII, users can create dynamic and flexible workflows that adapt to changing conditions and requirements. This powerful feature enables AI experts to create more sophisticated and adaptable AI solutions while leveraging AXII's robust infrastructure and resource management capabilities.