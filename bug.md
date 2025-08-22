# bug

Fix a bug using Test-Driven Development (TDD) methodology. This command guides Claude through researching the bug, writing a failing test, and then implementing the fix with user interaction at each phase.

## Usage

```
/bug <description>
```

## Arguments

- `description`: A detailed description of the bug, including:
  - What behavior is observed
  - What behavior is expected
  - Any error messages or symptoms
  - Steps to reproduce (if known)

## Examples

```
/bug The weather forecast command throws KeyError when API response is missing temperature data
/bug CLI command fails with "AttributeError: 'NoneType' object has no attribute 'location'" when fetching weather
/bug Weather alert command skips notifications when conditions change too rapidly
/bug Current conditions command returns stale data when location coordinates are invalid
/bug Weather history command shows incorrect timestamps when timezone conversion fails
```

## Process

### Phase 1: Research & Planning
1. Analyze the bug description to understand the problem
2. **Reproduce the bug:**
   - Run the actual CLI commands that trigger the issue
   - Document exact steps, inputs, and outputs
   - Capture error messages, stack traces, or unexpected behavior
3. Search the codebase to locate relevant code
4. Identify the root cause of the issue
5. Determine which files need modification
6. **Present findings to the user:**
   - Bug reproduction steps and results
   - Root cause analysis
   - Files that need to be modified
   - Recommended fix approach
7. **Wait for user approval before proceeding**

### Phase 2: Write Failing Test (TDD - Red)
1. Write a test that reproduces the bug scenario
2. Ensure the test captures the expected behavior
3. Place test in appropriate directory:
   - `tests/` following the existing test structure
   - Match the module structure (e.g., tests for `weather/cli/forecast/current.py` go in `tests/cli/forecast/test_current.py`)
4. Run the test to confirm it fails with the current code
5. **Present the failing test code and output to the user**
6. **Discuss the test approach and get user feedback**
7. **Only after user approval:** Commit ONLY the failing test with message:
   ```
   test: Add failing test for [bug description]

   This test demonstrates the bug where [specific issue].
   Expected: [expected behavior]
   Actual: [current broken behavior]

   🤖 Generated with Claude Code

   Co-Authored-By: Claude <noreply@anthropic.com>
   ```
8. **Wait for user confirmation before moving to implementation**

### Phase 3: Implement Fix (TDD - Green)
1. **Present the implementation approach to the user**
2. **After user approval:** Implement the minimal code change to make the test pass
3. Run the test to confirm it now passes
4. Run related tests to ensure no regressions
5. **Show the user the passing tests and implementation**
6. **Only after user approval:** Commit the fix with message:
   ```
   fix: [Concise description of what was fixed]

   Resolves issue where [bug description].
   The fix [brief explanation of the solution].

   🤖 Generated with Claude Code

   Co-Authored-By: Claude <noreply@anthropic.com>
   ```

### Phase 4: Refactor (TDD - Refactor) [Optional]
1. **If refactoring is needed, discuss with user first**
2. Implement agreed-upon refactoring
3. Ensure all tests still pass after refactoring
4. **Get user approval before committing**
5. Commit any refactoring separately

## User Interaction Points

The process includes explicit pauses for user interaction:

1. **After Research**: User reviews and approves the bug analysis and fix plan
2. **After Test Creation**: User reviews the failing test before it's committed
3. **After Test Commit**: User confirms readiness to proceed with implementation
4. **Before Fix Implementation**: User approves the implementation approach
5. **After Implementation**: User reviews the fix before it's committed
6. **Before Refactoring**: User decides if refactoring is needed

## Output

At each phase, Claude will provide:

### Phase 1 Output
- Summary of bug research findings
- Root cause analysis
- Proposed fix approach
- Files that will be modified

### Phase 2 Output
- The failing test code
- Test execution output showing the failure
- Explanation of what the test validates

### Phase 3 Output
- The fix implementation
- Test execution showing it now passes
- Any related tests that were run

### Phase 4 Output (if applicable)
- Refactoring changes
- Confirmation that all tests still pass

## Benefits

- **User Control**: User maintains oversight at each critical step
- **Test Coverage**: Ensures the bug fix includes a regression test
- **Documentation**: The test serves as documentation of the bug
- **Verification**: Confirms the fix actually resolves the issue
- **Clean History**: Separates test and implementation in git history
- **TDD Practice**: Follows red-green-refactor cycle with deliberate pacing

## Notes

- The test should be minimal and focused on the specific bug
- Follow existing test patterns in the codebase
- Use appropriate test fixtures and mocks as needed
- Avoid fixing unrelated issues in the same commit
- If the bug affects multiple areas, consider breaking into multiple bug fixes
- The test should fail for the right reason (the actual bug, not setup issues)
- User can skip phases or request modifications at any interaction point
