---
name: spec
description: Create a new specification file for the project
usage: /spec <feature_name> "<brief_description>"
example:
  - /spec weather_alerts_system "Enable automated weather alerts based on location and user preferences"
---

# Create New Specification: $ARGUMENTS

Creating a specification that enhances existing code with NO backward compatibility.

**NO CODE EXAMPLES** - Describe changes conceptually only.

## Specification Structure
1. **Overview & Objectives**: Problem statement and goals
2. **Current State Analysis**: What exists vs. what's needed  
3. **Architecture Design**: Implementation approach (conceptual)
5. **Implementation Phases**: Incremental development with acceptance criteria

## Phase Requirements
**CRITICAL**: Phase headers must use format `## Phase X: [Name]` for `/implement_phase` compatibility.

**Phase Design Principles**:
1. **Incremental**: Phase 1 should be the smallest buildable core functionality
2. **Buildable**: Each phase builds on previous phases  
3. **Testable**: Each phase includes comprehensive unit test requirements
4. **Measurable**: Each phase has specific acceptance criteria

Each phase includes:
- **Description**: What this phase accomplishes
- **Core Functionality**: Minimal viable feature set (behavior, not code)
- **Implementation Approach**: Which files to modify, what to add, how it integrates
- **Unit Test Requirements**: New tests to create, existing tests to modify
- **Acceptance Criteria**: Measurable success conditions

## File Creation
I'll create the specification file in `specs/` following the naming convention: `YYYY-MM-DD_HH-mm_<feature_name>.md`
- The date prefix uses today's date in YYYY-MM-DD_HH-mm format
- This ensures specs are chronologically ordered by creation date

Ready to proceed with creating the detailed specification for: **$ARGUMENTS**
