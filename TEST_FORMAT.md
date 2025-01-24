# JSON Logic Test Format

This document outlines the structure for specifying test cases for JSON Logic proposals. The format is designed to be human-readable, easily shareable, and machine-parsable. Each test is represented as a JSON object within an array.

## Structure of a Test Case

A test case should be a JSON object with the following fields:

- **`description`** *(string, required)*: A short, human-readable description of the test case that explains its purpose.
- **`rule`** *(any, required)*: The JSON Logic rule to be tested.
- **`data`** *(any, required)*: The input data that the rule will evaluate against. 

And either:

- **`result`** *(any, required)*: The expected result after evaluating the rule with the provided data.

OR

- **`error`** *(Partial\<Error\>, required)* - Communicates that it is expected that the logic will fail due to a hard error. This object must partial match against the error emitted.

`any` refers to any valid [RFC8259](https://datatracker.ietf.org/doc/html/rfc8259) value.

`string` refers to [strings in RFC8259](https://datatracker.ietf.org/doc/html/rfc8259#section-7).

`Error`, at this time, is defined as a JSON Object with a `type` property, defined as a string (e.g. `{ "type": "NaN" }`).

The test cases are stored as an array of these objects, allowing for multiple tests in a single file.

## Example Test Cases

Below are examples demonstrating how to format JSON Logic test cases:

### Basic Arithmetic Test

```json
[
  {
    "description": "Adds two numbers together",
    "rule": { "+": [1, 2] },
    "data": {},
    "result": 3
  }
]
```

### Data-Driven Logic

```json
[
  {
    "description": "Checks if a value is greater than 10",
    "rule": { ">": [{ "var": "value" }, 10] },
    "data": { "value": 15 },
    "result": true
  },
  {
    "description": "Fails if value is not greater than 10",
    "rule": { ">": [{ "var": "value" }, 10] },
    "data": { "value": 5 },
    "result": false
  }
]
```

### Compound Logic Test

```json
[
  {
    "description": "Combines AND and OR logic",
    "rule": {
      "and": [
        { ">": [{ "var": "x" }, 10] },
        { "or": [
          { "==": [{ "var": "y" }, 5] },
          { "==": [{ "var": "z" }, 7] }
        ] }
      ]
    },
    "data": { "x": 15, "y": 5, "z": 3 },
    "result": true
  }
]
```

### Error Logic Test

```json
[
  {
    "description": "Checks if division by zero fails",
    "rule": { "/": [0, 0] },
    "error": { "type": "NaN" },
    "data": null
  },
  {
    "description": "Checks if throw can be embedded in another operator",
    "rule": { "+": [1, { "throw": "Some error" }] },
    "error": { "type": "Some error" },
    "data": null
  }
]
```

## Commentary and Section Headers

Strings in the root array will be ignored by the JSON Logic test processor. This allows you to add comments or declare section headers to provide human-readable information in your test-suite. 

For example:

```json
[
  "Basic Arithmetic Tests",
  {
    "description": "Adds two numbers together",
    "rule": { "+": [1, 2] },
    "data": {},
    "result": 3
  },
  "Advanced Logic Tests",
  {
    "description": "Combines AND and OR logic",
    "rule": {
      "and": [
        { ">": [{ "var": "x" }, 10] },
        { "or": [
          { "==": [{ "var": "y" }, 5] },
          { "==": [{ "var": "z" }, 7] }
        ] }
      ]
    },
    "data": { "x": 15, "y": 5, "z": 3 },
    "result": true
  }
]
```

## Guidelines for Writing Tests

1. **Clarity**: Write clear and concise descriptions for each test case.
2. **Completeness**: Ensure the `rule` and `result` fields are always provided.
3. **Realism**: Where possible, use realistic data scenarios to demonstrate practical use cases.
4. **Diversity**: Include a variety of tests to cover edge cases, common scenarios, and unusual configurations.
5. **Validation**: Verify that the `result` field reflects the actual output of a JSON Logic engine for the given `rule` and `data`

## Contribution

To review currently accepted test files, please refer to the `tests/` directory in this repository. These files contain validated test cases that adhere to the format outlined in this document.

If you are contributing test cases, ensure they adhere to this format. Consistency across tests ensures smooth integration and validation.

Happy testing! 🚀

