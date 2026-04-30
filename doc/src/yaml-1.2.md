# YAML 1.2

Link: https://yaml.org/spec/1.2.2/

## Overview

YAML 1.2 has evolved to:

- Be a strict superset of JSON.
- Remove many obscure rules like implicit typings.

The general important [goals](https://yaml.org/spec/1.2.2/#goals) of YAML:

1. Be human-readable.
2. Be portable across languages.
3. Easy to parse/implement/use.

Context: PyYAML is generally considered the reference information. LibYAML is generally used in other YAML frameworks.

## Structure

To understand YAML, one should:

- Understand its information model, that is, the abstract model of how YAML decides to organize data.
- Translation of that information model to the YAML textual format.

## Features Overview

This section lists all features of YAML, to motivate the YAML specification later.

Three basic building blocks: Scalars, Sequences, Mappings.

### Syntax

#### Block Syntax

- Indentation is used for scope: Same indentation = Same list/hash.
- A line is used for specifying an entry within the list/hash.

Entry syntax:

- **Block sequences** use a dash and a space (`- `) for each entry.
- **Block mappings** use a colon and a space (`: `) for each key/value pair.

Comments use `#`.

Example:

```yaml
house_1:
  - person_1 # First entry of the first key/value pair
  - hrnax # Second entry of the first key/value pair
```

Example from the spec:

```yaml
- name: Mark McGwire
  hr: 65
  avg: 0.278
- name: Sammy Sosa
  hr: 63
  avg: 0.288
```

For a more compact representation, see [Compact Nested Mapping](#compact-nested-mapping).

#### Flow Syntax

- Indicators are used to denote scopes.
- Puntuations are used to denote entries.

Entry syntax:

- **Flow sequences** use a comma-separated list within square brackets.
- **Flow mappings** use a comma-separated list of key/value pairs within curly braces.

```yaml
flow mapping: { a: 1, b: 2 }

flow sequence:
  - [1, 2, 3]
  - [4, 5, 6]
```

#### Data Sharing

In data structures, it's common to have an object/list to be shared in more than one places.

YAML allows this by **anchors** (`&`) and **aliases** (`*`), kind of like C++ address-of and dereferencing operators.

Example from the spec:

```yaml
hr:
  - Mark McGwire
  # Following node labeled SS
  - &SS Sammy Sosa
rbi:
  - *SS # Subsequent occurrence
  - Ken Griffey
```

#### Complex Mapping Keys

Sometimes mapping keys need to be more than simple scalars, e.g using a list as a key.

A question mark and space (`? `) indicates a complex mapping key. Within a block collection, key/value pairs can start immediately following the dash, colon or question mark.

Example from the spec:

```yaml
? - Detroit Tigers
  - Chicago cubs
: - 2001-07-23

[New York Yankees, Atlanta Braves]: [2001-07-02, 2001-08-12, 2001-08-14]
```

#### Compact Nested Mapping

It's common to have a list of objects (e.g. a product catalog).

Within a block sequence, key/value pairs can start immediately after the dash, allowing compact representation of lists of mappings.

Example from the spec:

```yaml
# Products purchased
- item: Super Hoop
  quantity: 1
- item: Basketball
  quantity: 4
- item: Big Shoes
  quantity: 1
```

### Structures

YAML files can be made up of **directives** and **document content**.

- **Directives**: instructions for the YAML processor, not part of the data. YAML 1.2 defines 2 directives: `%YAML` (version) and `%TAG` (tag shorthands).
- **Document content**: the actual data described in the above section, such as scalars, sequences, and mappings.

Syntactically:

- `---` is used to separate directives from content, and signals start of a new document (even without directives, effectively just document separators).

  Example from the spec:

  ```yaml
  # Ranking of 1998 home runs
  ---
  - Mark McGwire
  - Sammy Sosa
  - Ken Griffey

  # Team ranking
  ---
  - Chicago Cubs
  - St Louis Cardinals
  ```

- `...` is used to signal the end of a document without starting a new one.

  Example from the spec:

  ```yaml
  ---
  time: 20:03:20
  player: Sammy Sosa
  action: strike (miss)
  ...
  ---
  time: 20:03:47
  player: Sammy Sosa
  action: grand slam
  ...
  ```
