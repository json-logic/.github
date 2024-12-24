# Technical Committee (TC) Process and Voting Guidelines

## Overview

This document describes the process for advancing proposals and the voting guidelines followed by the JSON Logic Technical Committee (TC).

## What is a Proposal? 

A proposal is a formal suggestion or plan introduced to the JSON Logic organization for consideration. 

Proposals typically aim to enhance, modify, or clarify JSON Logic functionality.

Within the scope of "JSON Logic Core", we will explore:
- The addition of a limited set of new operators.
- Clarifying the error boundaries for existing operators.
- Clarifying the behavior of operators.
- Parsing semantics.
- Modifiying operators for consistency.

Proposals may also cover things outside of JSON Logic Core. For example, 
- Introducing a community extension outside of Core, or operators to an extension.
- Amending organization procedures

## Proposal Lifecycle

Proposals in JSON Logic follow a structured lifecycle consisting of three phases:

### Phase 0: Proposal Status
- Proposals are introduced to the organization as discussions in the relevant repository.
- Each proposal must include:
  - Relevant background and use cases.
  - An exploration of potential roadblocks.
  - A test suite in the format described [here](/TEST_FORMAT.md).
- Proposals must adhere to previously ratified proposals, or explicitly supercede them.

### Phases 1-2: Validation / Implementation Status
- During these phases, proposals will be implemented in a few JSON Logic runtimes, if relevant.
- If significant friction is encountered or reasonable community concerns are raised, the proposal may be pulled back to Phase 0.

### Phase 3: Accepted
- For a proposal to move to Phase 3:
  - A predefined number of implementations (to be decided by the TC) must support the proposal.
  - The proposal must meet all other acceptance criteria established by the TC.

## Voting Guidelines

The TC uses a voting system to decide the advancement of proposals, inspired by https://www.apache.org/foundation/voting.html. 

The guidelines are as follows:

### Voting Scale
- Votes are represented by a range of `[-1..1]`:
  - `-1`: Constitutes a veto.
  - `[-0..-1)`: Represents non-blocking distaste for a proposal.
  - `(0..1]`: Represents a positive vote.

### Proposal Advancement Requirements
To advance a proposal from Phase 0 to Phase 1:
1. **Positive Votes**: A minimum of three positive votes must be received from TC members.
2. **Aggregate Vote**: The aggregate score of votes must be positive.
3. **Vetoes**: There must be no vetoes (`-1` votes from members of the TC).

Community members are encouraged to cast votes, as their votes will be counted towards the aggregate.

## Technical Committee Members

The current TC members are as follows:

| GitHub Handle | Name | Background |
|---------------|------|------------|
| [@TotalTechGeek](https://github.com/TotalTechGeek) | Jesse Mitchell | Project Maintainer; Initiative Organizer |
| [@codetiger](https://github.com/codetiger) | Harishankar Narayanan | Project Maintainer; Working on Compat Table |
| [@gregsdennis](https://github.com/gregsdennis) | Greg Dennis | Project Maintainer; Active in multiple RFCs |
| [@toddbaert](https://github.com/toddbaert) | Todd Baert | JSON Logic User; OpenFeature TC Member |
| [@jwadhams](https://github.com/jwadhams) | Jeremy Wadhams | **JSON Logic Creator** |

## Conclusion

The JSON Logic TC process is designed to ensure that proposals are thoroughly evaluated and widely supported before being accepted. 

By adhering to this structured process, we aim to maintain the stability and reliability of JSON Logic while fostering innovation.

