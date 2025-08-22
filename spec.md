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
ls -la weather/
```

Based on the project's integration philosophy, I'll create a specification that:

## Direct Integration Approach
• **Enhance Existing Code**: Modify current files rather than creating parallel systems
• **No Backward Compatibility**: Unless explicitly requested, new features become default behavior
• **Follow Existing Patterns**: Integrate with current architecture and conventions

## Specification Creation Guidelines
1. Only use coding examples when they are necessary to explain the purpose of a piece of logic.

## Specification Structure
The specification will include:

1. **Overview & Objectives**: Clear problem statement and goals
2. **Current State Analysis**: What exists vs. what's needed
3. **Architecture Design**: Brief, but thorough description of implementation approach (no code, mermaid charts where appropriate)
4. **Integration Strategy**: How will existing implementations be used and integrated with
5. **Configuration Changes**: Environment variables, dependencies, settings [If applicable]
7. **Acceptance Criteria**: Measurable success conditions

## Implementation Guidelines
• All code changes integrate directly into existing files
• Look for way to use pythonic practices to keep it simple
• Follow the project's dataclass and type annotation patterns
• Include simple but broad coverage error handling and logging

## File Creation
I'll create the specification file in `specs/` following the naming convention: `YYYY-MM-DD_hh_mm<feature_name>.md`
- The date prefix uses today's date in YYYY-MM-DD-hh_mm format
- This ensures specs are chronologically ordered by creation date

Ready to proceed with creating the detailed specification for: **$ARGUMENTS**
