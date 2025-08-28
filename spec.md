---
name: spec
description: Create a new specification file for the project
usage: /spec <feature_name> "<brief_description>"
example:
  - /spec weather_alerts_system "Enable automated weather alerts based on location and user preferences"
---

# Create New Specification: $ARGUMENTS

I'll create a comprehensive specification for this feature following this project's standards.

Let me analyze the existing codebase structure and create a specification that integrates directly with the current implementation:

```bash
find specs/ -name "*.md" -type f | head -3
```

```bash
ls -la src/dollas/
```

Based on the project's integration philosophy, I'll create a specification that:

## Direct Integration Approach
- **Enhance Existing Code**: Modify current files rather than creating parallel systems
- **NO BACKWARD COMPATIBILITY - EVER**: New features ALWAYS replace old behavior completely. Breaking changes are preferred over compatibility layers. If users need to update configs, scripts, or code - that's intentional and good.
- **Follow Existing Patterns**: Integrate with current architecture and conventions

## Specification Structure
The specification will include:

1. **Overview & Objectives**: Clear problem statement and goals (explicitly state NO backward compatibility if breaking changes)
2. **Current State Analysis**: What exists vs. what's needed
3. **Architecture Design**: Brief, but thorough description of implementation approach (explain changes conceptually, use mermaid charts where appropriate but NO code examples)
4. **Breaking Changes Section** (if applicable): When the feature introduces breaking changes, explicitly list what will break and what users must update
5. **Configuration Changes**: Environment variables, dependencies, settings
6. **Implementation Phases**: Incremental development phases with integrated acceptance criteria

**IMPORTANT**: This specification should NOT include code examples. Instead, explain:
- What changes need to be made to existing files
- What new components or functions need to be added
- How the changes integrate with existing patterns
- The logic and behavior expected from each change

## Implementation Phases Structure
Each phase must follow this incremental design:

### Phase Design Principles
1. **Incremental**: Phase 1 should be the smallest buildable core functionality
2. **Buildable**: Each phase builds on previous phases
3. **Testable**: Each phase includes comprehensive unit test requirements
4. **Measurable**: Each phase has specific acceptance criteria

### Phase Naming and Formatting Requirements

**CRITICAL**: For `/implement_phase` command compatibility, phases MUST follow this exact format:

#### Phase Headers
- Use markdown headers (# ## ### ####) followed immediately by "Phase" and a colon
- Format: `## Phase 1: [Descriptive Name]` or `### Phase 2: [Descriptive Name]`
- The word "Phase" MUST be present in the header
- Use consistent header levels (recommend ## or ###)

#### Completion Marking
- When completed, append `[COMPLETED: git-sha]` to the phase header
- Example: `## Phase 1: Core Data Structure [COMPLETED: a1b2c3d]`
- The `/implement_phase` command will automatically add this when phases finish

#### Example Phase Headers
```markdown
## Phase 1: Basic Configuration Loading
## Phase 2: Data Validation Layer
## Phase 3: Error Handling and Logging [COMPLETED: f4e5d6c]
## Phase 4: Integration Testing
```

### Phase Template
For each phase, include:

**Phase X: [Phase Name]**
- **Description**: Brief overview of what this phase accomplishes
- **Core Functionality**: The minimal viable feature set for this phase (describe behavior, not code)
- **Dependencies**: What previous phases or existing code this builds on
- **Implementation Approach**: 
  - Which existing files need modification
  - What new functions or classes to add (describe purpose, not implementation)
  - How the changes integrate with current patterns
  - Expected behavior and logic flow
- **Unit Test Requirements**:

  New Tests to Create:
  1. **test_should_create_baseline_calculator_with_config**
     - Purpose: Verify calculator initialization with config
     - Input: Config with window_minutes=10
     - Expected: Calculator instance with window=10
     - What it validates: Proper configuration handling

  Tests to Modify:
  1. **test_existing_function_name**
     - Current behavior: Describe what it currently tests
     - Required change: Explain what needs to be updated
     - New validation: What additional behavior to verify

- **Acceptance Criteria**:
  - Measurable success conditions
  - Performance requirements (if applicable)
  - User-facing behavior validation

**Note on Testing**: 
- Clearly separate **New Tests** from **Tests to Modify**
- For new tests: Explain the purpose and what behavior they validate
- For modified tests: Describe current behavior and what changes are needed
- Mark testable components and behaviors with clear annotations (e.g., "This component should validate...", "Edge case: when X happens...")
- These specifications will be used when running `/spec-tests` command later
- Do NOT include test implementation code - focus on describing what needs to be tested and why

**REMINDER: NO CODE EXAMPLES**: Explain changes conceptually. Describe what modifications are needed, where they fit in the architecture, and how they should behave - but do not write actual code snippets.

## Implementation Guidelines
- All code changes integrate directly into existing files
- Follow the project's dataclass and type annotation patterns
- Maintain configurability through environment variables
- Include comprehensive error handling and logging
- **DO NOT INCLUDE CODE EXAMPLES**: Focus on explaining what needs to change, where it fits, and how it should behave
- Describe modifications at a conceptual level, identifying files to change and explaining the logic

## File Creation
I'll create the specification file in `specs/` following the naming convention: `YYYY-MM-DD_HH-mm_<feature_name>.md`
- The date prefix uses today's date in YYYY-MM-DD_HH-mm format
- This ensures specs are chronologically ordered by creation date

Ready to proceed with creating the detailed specification for: **$ARGUMENTS**
