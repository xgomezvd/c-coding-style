# Programming Philosophy

This document describes the general principles that guide my programming
decisions. These principles should influence implementation, design, and code
organization.

They are guidelines for making engineering decisions, not rigid rules that must
be followed regardless of context.

## Simplicity

- Prefer the simplest implementation that correctly solves the problem.
- Avoid unnecessary operations, conditions, variables, intermediate steps,
  abstractions, and layers of indirection.
- Do not introduce complexity unless it provides a tangible benefit.

See [simplicity examples](../examples/simplicity.md).

## Code Reduction and Readability

- Prioritize readability: code should be understandable in the shortest
  possible time.
- Minimize the amount of code necessary to understand an operation.
- Prefer concise implementations, but never sacrifice readability merely to
  reduce the total number of lines.
- A shorter implementation is not necessarily a simpler implementation. Avoid
  compressing code when doing so makes its purpose, behavior, or execution flow
  harder to understand.
- Prefer direct expressions of intent over unnecessary intermediate variables,
  conditions, or control structures.
- Avoid introducing intermediate variables and redundant error handling when
  they do not add any behavior or value.

## Homogeneity and Consistency

- Maintain consistent naming, interfaces, and implementation patterns across
  related components.
- However, homogeneity must not be achieved by introducing unnecessary
  functionality or artificial uniformity.
- For example, modules or plugins implementing the same interface should use
  consistent function names for the operations they support.
- If a particular module or plugin does not need to implement an optional
  operation, it should not be forced to provide an empty or meaningless
  implementation simply to match the other plugins.
- Prefer consistency where it provides value, while allowing legitimate
  differences between components.

## Functions and Code Organization

- Prefer small functions, particularly when they are reused in multiple places.
- However, do not split code into separate functions merely to give an existing
  block of code a descriptive name.
- A function should have a meaningful purpose beyond simply wrapping a few lines
  of code.
- Avoid excessive fragmentation. When a sequence of operations forms a coherent
  and easily understandable flow, keeping those operations together may be
  preferable to distributing them across several small functions.
- Function extraction should be justified by reuse, meaningful separation of
  responsibilities, or a genuine improvement in readability and maintainability.

## General Design Approach

- Favor straightforward implementations over unnecessary sophistication.
- Do not introduce abstractions, generic interfaces, helper functions, or
  additional layers merely because they are commonly considered good software
  engineering practices.
- Evaluate each design decision according to the actual benefit it provides to
  the codebase.
- The ultimate goal is to produce code that is simple, concise, homogeneous, and
  easy to understand.
- Where these rules do not specify a preference, follow the surrounding style.
- Avoid introducing new dependencies unless clearly justified.

## Economy of Structure

- The structure should serve the content, not the other way around.
- Avoid unnecessary structure, organization, and categorization.
- Do not introduce additional layers, files, abstractions, or documentation
  unless they provide meaningful value.
- Avoid repeating information that is already sufficiently expressed elsewhere.
- Prefer compact, cohesive documentation over excessive fragmentation. The
  organization should make information easier to understand and maintain, not
  become an additional burden.