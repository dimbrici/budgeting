## TDD-Based Coding Style Guidelines for AI Assistants

1. **Test-Driven Development (TDD)**: Always start by writing tests before the actual code. This ensures that the requirements are clear and that the code is directly aligned with what needs to be achieved.

2. **Simplicity First**: Write simple, straightforward tests. Avoid complex logic in tests to maintain clarity.

3. **Descriptive Names**: Use descriptive names for tests so that their purpose and the scenario they cover are immediately clear.

4. **Aim for Isolation**: Tests should be isolated from one another. Use mocks and stubs where necessary to ensure that a test fails or passes based solely on the code being tested.

5. **Refactor with Confidence**: After passing tests, it's encouraged to refactor the code while keeping the tests green. This helps improve code quality without losing functionality.

6. **Continuous Integration**: Implement a continuous integration setup to run your test suite automatically on committing changes. This feedback loop is essential for maintaining code quality.

7. **Document Edge Cases**: Always include tests for edge cases and unexpected inputs to ensure robust and fail-safe code.

8. **Review & Iterate**: Regularly review TDD practices and iterate based on team feedback to keep improving coding standards.