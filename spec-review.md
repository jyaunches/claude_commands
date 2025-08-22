# Spec Review

Review a specification file for simplification opportunities, pythonic patterns, and architectural alignment.

## Arguments

- spec_path: Path to the specification file (use @ for file suggestions)

## Usage

```bash
/spec_review @specs/2025-01-08_weather_api_integration.md
/spec_review @specs/features/weather_alerts_system.md
```

You can type `/spec_review @` and Claude will provide file path suggestions as you type.

## Description

This command performs a comprehensive review of a specification file to:

1. **Simplify Design**: Identify overly complex approaches and suggest simpler alternatives
2. **Pythonic Patterns**: Recommend Python-specific patterns and libraries (stdlib and 3rd party)
3. **Architecture Alignment**: Find opportunities to reuse existing code or align with current patterns
4. **Implementation Questions**: Highlight areas that need clarification before implementation. Across all of these, give options and make a recommendation. Explain your recommendation.
5. **Conciseness**: Suggest ways to make the spec more focused and actionable

The review focuses on:
- Using Python's built-in features effectively (dataclasses, context managers, etc.)
- Leveraging existing libraries instead of reinventing wheels
- Identifying patterns in the current codebase that could be reused
- Simplifying architectural decisions where possible
- Ensuring the spec is actionable and not over-engineered

## Output

The command returns a structured review with:
- **Simplification Opportunities**: Specific suggestions to reduce complexity
- **Pythonic Improvements**: Better ways to leverage Python features
- **Reuse Opportunities**: Existing code that could be leveraged
- **Implementation Questions**: Areas needing clarification
- **Recommended Libraries**: Python packages that could simplify implementation
