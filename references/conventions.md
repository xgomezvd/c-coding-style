# Coding Conventions

## Alignment

- Use a small number of spaces to align lines that are similar in both structure
  and meaning, subject to the variable alignment rules below.

## Includes

- Group includes in this order: system headers, third-party headers, then
  repository headers grouped by top-level directory.
- Do not insert blank lines between include groups.
- Within each group, sort header paths by increasing length.
- Preserve ordering required for compilation.

## Variable declarations

- Measure declaration length using the type, name, and initializer, if present.
  Ignore indentation and extra spaces added for alignment.
- Order declarations from longest to shortest. Length takes priority over
  grouping related variables; use relationships to order equal-length
  declarations.
- Align variable names and, where present, assignment operators in global
  declarations.
- Declare local variables at the beginning of the function.
- Align local variable names and, where present, assignment operators only
  when there are six or more variables declared at the beginning of the
  function. Count all variables in that opening block, not each related group.
- When checking a function's return value for NULL or an error, put the
  assignment inside the if condition if the complete if statement header
  fits within 80 characters. Keep the variable declaration at the beginning
  of the function and parenthesize the assignment explicitly.

## Struct initializers

- Format repeated struct initializers as compact tables.
- Use spaces to align corresponding fields across structurally similar rows.
  Right-align numeric fields, such as counts.
- Place nested arrays on separate lines when this makes their roles clearer,
  aligning their opening braces within each initializer.
- Add small amounts of padding to align comparable values and make patterns
  and differences easy to scan.
- Apply alignment locally to similar rows or groups; do not force every row
  into a rigid table with excessive whitespace.

## Types and allocations

- Prefer fixed-width integer types (`uint64_t`, `int32_t`, etc.) when size 
  matters.
- Check errors explicitly.
- Avoid unnecessary dynamic allocation.
- Prefer stack allocation for small, bounded objects.

## Naming

- Prefer short names that still make the variable's or function's purpose clear.
- Functions and variables: `snake_case`.
- Struct types: `<name>_t`.
- Enum types: `<name>_e`.
- Constants/macros: `UPPER_CASE`.

## Functions

- Prefer early returns instead of deeply nested `if` statements.

## Comments

- Do not comment what the code obviously does.
- Comments should explain why something is necessary or non-obvious.
- Document assumptions, hardware limitations, and platform-specific behavior.

## Changes

- Do not perform unrelated refactoring.
- Preserve compatibility unless explicitly asked otherwise.
- Do not reformat unrelated code to enforce these rules.

## Project-specific preferences

- When dealing with hardware counters, clearly distinguish raw counters,
  accumulated values, deltas, and derived metrics.