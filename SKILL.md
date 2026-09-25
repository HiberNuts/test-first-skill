---
name: test-first
description: Write focused failing tests before implementing behavior changes or bug fixes. Use when code has observable outcomes to protect, including relevant failure paths; use mocks for external dependencies when needed.
license: MIT
---

# Test first

1. **Choose cases from the contract.** Trace the affected path and inspect existing tests before editing production code. Identify success, boundaries, and relevant failures such as invalid input, denied access, missing data, dependency errors, retries, or duplicate delivery. Include forbidden side effects. Keep one case per distinct risk; reuse or extend existing tests.
2. **Write tests before code.** Test observable outcomes through the closest useful boundary. Use unit tests for pure logic and integration tests when authorization, persistence, state transitions, or wiring matters. Mock external services, responses, clocks, or other dependencies to make difficult cases deterministic. Keep the behavior under test real; use an isolated test database for changed persistence rules. Restore altered globals.
3. **Prove the red phase.** Run the focused tests before the production edit. A new test must fail for the expected behavioral reason; fixture and environment failures do not count. An existing failing test also counts. If a case passes already, reassess its value. Never change code to manufacture a failure.
4. **Make it green.** Implement the smallest change and rerun the focused tests. Add another case only for a distinct missed outcome. Avoid implementation-detail assertions, broad snapshots, duplicate scenarios, and coverage targets.
5. **Report the evidence.** State what failed before the change and passed after it. If no meaningful automated test can be written or run, explain why and use the narrowest useful check.
