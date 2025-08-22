# spec-tests

Write comprehensive test specifications for an existing spec file using TDD principles.

## Usage

```
/spec-tests @<spec-file> [instructions]
```

## Arguments

- `spec-file`: Path to the specification file to write tests for (use @ to trigger file selection)
- `instructions`: Optional focus areas for the test strategy

## Examples

```
/spec-tests @specs/2025-01-15_weather_api_integration.md
/spec-tests @specs/forecast_alerts_system.md "Focus on edge cases for notification handling"
/spec-tests @specs/location_weather_search.md "Prioritize integration tests"
```

## Process

### Phase 1: Analyze & Design Test Strategy

1. Read and analyze the specification file
2. Review existing test patterns in `tests/`
3. Design test coverage:
   - **Unit Tests**: Isolated component testing with mocks
   - **Integration Tests**: CLI workflow testing end-to-end
   - **Edge Cases**: Boundary conditions and error scenarios
4. Identify reusable patterns (fixtures, mocks, parametrization)
5. Present strategy to user with coverage overview and recommendations
6. Discuss and adjust based on user feedback
7. Wait for approval before proceeding

### Phase 2: Write Test Specification

1. Create test specification document outlining:
   - Test file organization
   - Test classes with purpose and scope
   - Input/output data structures
   - Mock configurations needed
2. Follow testing best practices:
   - Clear naming: `test_should_X_when_Y`
   - One assertion focus per test
   - Proper fixture usage
   - Behavior over implementation
3. Save as `YYYY-MM-DD_<feature_name>_tests.md` in `specs/`

## Test Strategy Output Template

```markdown
## Test Strategy for [Spec Name]

### Coverage Overview
- Components to test: X
- Estimated test count: Y
- Unit tests: List key components
- Integration tests: List workflows to verify

### Key Testing Challenges
- External service mocking
- Data format variations
- Edge case handling

### Recommendations
- Priority areas for testing
- Suggested parametrization
- Reusable fixtures needed
```

## Integration Test Guidelines

Integration tests verify complete CLI workflows from command to persistence:

- **Purpose**: Test full command execution paths
- **Pattern**: Chain CLI commands to verify end-to-end functionality
- **Goal**: Maximize coverage per test to minimize test count

### Example Pattern

```python
def test_weather_forecast_workflow(cli_runner, mock_api):
    """Test: fetch forecast → verify data → display results."""

    # Fetch weather forecast
    result = cli_runner.invoke(app, ["forecast", "New York"])
    assert result.exit_code == 0

    # Verify forecast data
    result = cli_runner.invoke(app, ["status", "locations"])
    assert "New York" in result.output

    # Test current conditions
    result = cli_runner.invoke(app, ["current", "New York"])
    assert result.exit_code == 0
```

### Best Practices

1. Test complete workflows, not single commands
2. Mock at API boundaries, let internal logic run
3. Verify side effects (persistence, file creation)
4. Keep tests fast (<1 second per test)

## User Interaction Points

1. **After Strategy**: Review and approve approach
2. **During Discussion**: Request priority changes
3. **Before Writing**: Confirm readiness
4. **After Creation**: Review specification

## Notes

- Review existing patterns in `tests/` directory
- Keep tests simple and behavior-focused
- Design for reusability from the start
- User can skip phases or modify at any point
