# Spec Review

Review a specification and its test specification for implementation clarity and design improvements using a two-phase process.

## Arguments

- spec_path: Path to the specification file (use @ for file suggestions)
- test_spec_path: Path to the test specification file (use @ for file suggestions)

## Usage

```bash
/spec_review @specs/2025-01-08_weather_api_integration.md @specs/tests_2025-01-08_weather_api_integration.md
/spec_review @specs/features/weather_alerts_system.md @specs/tests_weather_alerts_system.md
```

You can type `/spec_review @` and Claude will provide file path suggestions as you type.

## Description

This command performs a comprehensive review of both a specification file and its test specification using a **two-phase process** that requires user confirmation at each step:

### Phase 1: Implementation Review
Reviews both spec and test spec for implementation clarity:
1. **Implementation Questions**: Highlight areas that need clarification before implementation
2. **Test Coverage Gaps**: Identify missing test scenarios or unclear test requirements
3. **Phase Alignment**: Ensure test phases align properly with implementation phases

#### Output
This phase returns each Implementation Question in a structured table format:

**Question: [Clear statement of what needs to be decided]**

| Option | Description | Benefits | Tradeoffs | Complexity |
|--------|-------------|----------|-----------|------------|
| A | Brief description | Key benefit summary | Main tradeoff summary | Low |
| B | Brief description | Key benefit summary | Main tradeoff summary | Medium |
| C | Brief description | Key benefit summary | Main tradeoff summary | High |

**💡 Recommendation:** Option [X] - [Clear reasoning with specific benefits]

**Additional Details:**
- **Option A Benefits:** • Benefit 1 • Benefit 2
- **Option A Tradeoffs:** • Tradeoff 1 • Tradeoff 2
- **Option B Benefits:** • Benefit 1 • Benefit 2
- **Option B Tradeoffs:** • Tradeoff 1 • Tradeoff 2

This format provides a clean overview table followed by detailed breakdowns for better terminal readability.

#### User Interaction
After presenting Phase 1 recommendations, ask if the user wants to:
- Accept all recommendations and update both spec files
- Discuss specific items individually (with confirmation after each change)
- Proceed to Phase 2 without changes

### Phase 2: Design Review
Reviews both spec and test spec for fundamental design improvements:
1. **Simplify Design**: Identify overly complex approaches and suggest simpler alternatives
2. **Pythonic Patterns**: Recommend Python-specific patterns and libraries (stdlib and 3rd party)
3. **Architecture Alignment**: Find opportunities to reuse existing code or align with current patterns
4. **Conciseness**: Suggest ways to make each spec more focused and actionable

#### Output
This phase returns a structured review across both spec and test spec with:
- **Simplification Opportunities**: Specific suggestions to reduce complexity
- **Pythonic Improvements**: Better ways to leverage Python features
- **Reuse Opportunities**: Existing code that could be leveraged
- **Recommended Libraries**: Python packages that could simplify implementation

#### User Interaction
After presenting Phase 2 recommendations, ask if the user wants to:
- Accept all recommendations and update both spec files
- Discuss specific items individually (with confirmation after each change)
- Complete the review without further changes

## Process Flow

1. **Start Phase 1**: Present all implementation questions and test coverage gaps
2. **User Choice**: Accept all, discuss individually, or skip to Phase 2
3. **Discussion Loop**: If discussing individually, present remaining items after each change
4. **Update Files**: Apply changes to both spec and test spec files based on feedback
5. **Phase 1 Complete**: Confirm all Phase 1 items are resolved
6. **Start Phase 2**: Present all design recommendations
7. **User Choice**: Accept all, discuss individually, or complete
8. **Discussion Loop**: If discussing individually, present remaining items after each change
9. **Update Files**: Apply changes to both spec and test spec files based on feedback
10. **Review Complete**: Summarize all changes made to both files

## Focus Areas

The review focuses on:
- Using Python's built-in features effectively (dataclasses, context managers, etc.)
- Leveraging existing libraries instead of reinventing wheels
- Identifying patterns in the current codebase that could be reused
- Simplifying architectural decisions where possible
- Ensuring the spec is actionable and not over-engineered
- Clarifying implementation details and technical decisions

## Output Format

Each phase will present structured recommendations with:
- **Category**: Which review area the recommendation addresses
- **Current Approach**: What the spec currently describes
- **Recommended Change**: Specific suggestion for improvement
- **Rationale**: Why this change would be beneficial
- **Impact**: How this affects other parts of the spec or implementation
