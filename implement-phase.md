---
name: implement_phase
description: Execute implementation phases from a specification file using test-driven development
usage: /implement_phase <spec_file_path>
examples:
  - /implement_phase specs/2025-01-08_weather-api-integration.md
  - /implement_phase specs/2024-12-15_storm-alert-system.md
---

# Implement Phase: $ARGUMENTS

I'll execute the implementation phases from the specified specification file following a rigorous test-driven development workflow.

Let me start by analyzing the specification file and identifying the current phase status:

```bash
find specs/ -name "*$(basename $ARGUMENTS .md)*" -type f
```

```bash
grep -n "Phase.*:" "$ARGUMENTS" | head -10
```

```bash
grep -n "\[COMPLETED:" "$ARGUMENTS" || echo "No completed phases found"
```

## Phase Execution Workflow

For each unfinished phase, I will follow this exact 7-step pattern:

### Step 1: Phase Review & Alignment
- **Review the phase** to understand scope and requirements
- **Review how/where to write unit tests** - look for existing unit tests to modify, ways to improve/reduce number of tests with pythonic strategies, reusable modules or fixtures to keep consistency across tests
- **Present TDD based approach to user** - Present plan for the incremental writing of the tests and actual code to complete the phase
- **Implementation Questions**: Highlight areas that need clarification before implementation. Across all of these, give options and make a recommendation. Explain your recommendation.
- **WAIT for user confirmation** before proceeding to implementation

### Step 2: Write Tests First
- **Write comprehensive tests** covering all unit test requirements from the phase
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
awk '/^#{1,4}.*Phase.*:/ { phase=$0; getline; content=$0; if(phase !~ /COMPLETED:/) { print "NEXT PHASE:", phase; exit } }' "$ARGUMENTS"
```

Based on my analysis of the specification file, I'll now begin **Step 1: Phase Review & Alignment** for the next unfinished phase.

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

Ready to analyze the first unfinished phase from: **$ARGUMENTS**
