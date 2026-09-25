---
name: test-first
description: Write focused failing tests before implementing behavior changes or bug fixes. Use when code has observable outcomes to protect, including relevant failure paths; use mocks for external dependencies when needed.
license: MIT
---

# Test first

Apply this workflow to behavior changes and bug fixes. For a pure refactor, establish passing behavior checks before and after; do not invent a failure. Documentation and formatting changes need no new behavior tests.

1. **Choose cases from the contract.** Trace the affected path and inspect existing tests before editing production code. Derive expected results from requirements, not from the current implementation or the same helper being tested. Identify success, boundaries, and relevant failures such as invalid input, denied access, missing data, dependency errors, retries, or duplicate delivery. Include forbidden side effects. Reuse or extend existing tests; each added case should protect a distinct risk.
2. **Write tests before code.** Test observable outcomes through the closest useful boundary. Use unit tests for pure logic and integration tests when authorization, persistence, state transitions, or wiring matters. Mock external services, responses, clocks, or other dependencies to make difficult cases deterministic. Use realistic responses and errors, keep the behavior under test real, and assert the resulting state or output rather than only that a mock was called. Use an isolated test database for changed persistence rules. Restore altered globals and test state.
3. **Prove the red phase.** Run the focused tests before the production edit. The test exposing the bug or missing behavior must fail for the expected reason; fixture and environment failures do not count. An existing failing test also counts. Tests preserving existing behavior may already pass. If the intended regression test passes, reassess the reproduction or requirement before coding. Never change code to manufacture a failure.
4. **Make it green.** Implement the smallest change, then run the focused tests and relevant existing regression tests. Do not weaken assertions, skip a failing test, or change expected results merely to get green; correct a mistaken test only with a reason grounded in the requirement. Add another case only for a distinct missed outcome. Avoid implementation-detail assertions, broad snapshots, duplicate scenarios, and coverage targets.
5. **Report the evidence.** Give the test commands and observed red and green results. If a meaningful automated check cannot be written or run, state the blocker, use the narrowest useful alternative, and identify what remains unverified. Never count a skipped or unrun test as passing.
