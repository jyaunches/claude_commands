---
name: implement_phase
description: Execute implementation phases from specification and test specification files using test-driven development
usage: /implement_phase <spec_file_path> <test_spec_file_path>
examples:
  - /implement_phase specs/2025-01-08_weather-api-integration.md specs/tests_2025-01-08_weather-api-integration.md
  - /implement_phase specs/2024-12-15_storm-alert-system.md specs/tests_2024-12-15_storm-alert-system.md
---

# Implement Phase: $ARGUMENTS

I'll execute the implementation phases from the specified specification and test specification files following a rigorous test-driven development workflow.

Let me start by analyzing both files and identifying the current phase status:

```bash
echo "Specification files:"
echo "Spec: $1"
echo "Test Spec: $2"
```

```bash
echo "\n=== Phases in Specification ===" 
grep -n "Phase.*:" "$1" | head -10
```

```bash
echo "\n=== Completed Phases ==="
grep -n "\[COMPLETED:" "$1" || echo "No completed phases found"
```

```bash
echo "\n=== Test Phases Available ===" 
grep -n "Phase.*:" "$2" | head -10
```

## Phase Execution Workflow

For each unfinished phase, I will follow this exact 7-step pattern:

### Step 1: Phase Review & Alignment
- **Review the phase** to understand scope and requirements
- **Review how/where to write unit tests** - look for existing unit tests to modify, ways to improve/reduce number of tests with pythonic strategies, reusable modules or fixtures to keep consistency across tests
- **Present TDD based approach to user** - Present plan for the incremental writing of the tests and actual code to complete the phase
- **WAIT for user confirmation** before proceeding to implementation

### Step 2: Write Tests First
- **Use test specification** to write tests from the corresponding phase in the test spec file
- **Follow test guide exactly** including existing tests to modify and new tests to create
- **Ensure tests fail** (red phase of TDD)
- **Commit failing tests** with descriptive commit message

### Step 3: Implement Code
- **Write minimal code** to make tests pass (green phase of TDD)
- **Follow existing patterns** and integrate with current architecture
- **Only implement** what's necessary to pass the tests

### Step 4: Commit Implementation
- **Verify all tests pass**
- **Commit the implementation** with descriptive commit message

### Step 5: Validate Acceptance Criteria
- **Review phase acceptance criteria**
- **Determine if additional test/implementation cycles** are needed
- **Repeat steps 2-4** if criteria require more functionality

### Step 6: Phase Completion Review
- **Present completed phase** for your review
- **Get explicit agreement** that the phase meets all requirements
- **Confirm phase is ready** to mark as complete

### Step 7: Update Specification
- **Mark phase as completed** in spec file: `[COMPLETED: git-sha]`
- **Include the final commit SHA** from the phase
- **Commit spec file update**

## Current Phase Analysis

Let me identify the next phase to implement and begin the workflow:

```bash
# Find the first phase that isn't marked as COMPLETED
echo "\n=== Next Phase Analysis ==="
awk '/^#{1,4}.*Phase.*:/ { phase=$0; getline; content=$0; if(phase !~ /COMPLETED:/) { print "NEXT PHASE:", phase; exit } }' "$1"
```

Based on my analysis of both the specification file and test specification file, I'll now begin **Step 1: Phase Review & Alignment** for the next unfinished phase.

## Implementation Strategy

Following the project's integration philosophy:
- **Direct integration** into existing files
- **No backward compatibility** - always direct integration
- **No parallel systems** - enhance current code
- **Follow existing patterns** and conventions
- **Use uv for dependencies** (never pip install)
- **Maintain type annotations** and dataclass patterns

## Phase Analysis & Approval Process

I will first analyze the phase and present a detailed implementation plan. **I will NOT proceed with implementation until you explicitly approve the approach.**

This allows for:
- Discussion of implementation strategy
- Refinement of the approach based on your feedback
- Alignment on technical decisions before coding begins

Ready to analyze the first unfinished phase from:
- **Specification**: $1  
- **Test Specification**: $2
