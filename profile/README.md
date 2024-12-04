# JSON Logic Community 🤝✨

Welcome to the *JSON Logic Community*! Our mission is to foster collaboration among maintainers and users of JSON Logic implementations across platforms to develop a more *rigorous specification*, promote compatibility, and provide resources that make JSON Logic more robust and beneficial to everyone.


## Why This Organization Exists 🌍
JSON Logic has become a popular standard for expressing conditional logic in a JSON-friendly format. However, over time, inconsistencies and ambiguities have emerged between different implementations, making it challenging for developers to rely on JSON Logic across platforms.

## Our Goals 🚀

1. **Develop a Rigorous Specification**
- Address ambiguities and inconsistencies in the current spec.
- Define behaviors for edge cases (e.g., truthiness, accessing nested data).

2. **Build Compatibility Resources**
- Create and maintain a compatibility table for implementations.
- Provide a robust test suite for maintainers to validate their projects.

3. **Support JSON Logic Maintainers**
- Offer resources and community support to help resolve implementation differences.
- Facilitate collaboration between maintainers to align on common goals.

4. **Encourage Extensibility**
- Identify and spec out common extensions.
- Release shared libraries or guidelines for extending JSON Logic.

## Key Challenges We Aim to Address 🧩

Here are some examples of challenges we’re working on:

- Accessing keys like `{ '': 1 }` or `{ 'hello.world': 1 }`.
- Truthiness quirks, such as `{ "!": [0] }` vs `{ "!": 0 }`; and `{ "!": { "var": "data" } }`, where `data` is an array.
- Handling iterator contexts (e.g., accessing parent context in filter operations).
- Defining behaviors for .length and similar properties in var operations.
- Aligning on reserved operators and backwards-compatible extensions.

## How You Can Help ❤️

We believe in the power of open collaboration! Here's how you can contribute:

1. **Join the Conversation**
- Participate in discussions to shape the specification and resolve ambiguities.

2. **Submit Feedback**
- Share issues, quirks, or use cases you've encountered with JSON Logic.

3. **Contribute to Resources**
- Help build the compatibility table or improve the test suite.

4. **Later on, participate in extension discussions**

## Get Involved! 🎉

Whether you’re a project maintainer, developer, or JSON Logic enthusiast, we’d love to have you onboard!
