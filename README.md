# Claude Code Commands

A collection of custom commands for Claude Code to streamline development workflows. These commands provide structured approaches for common development tasks including bug fixing, specification creation, testing, and feature development.

## Example Context

All examples in these commands are derived from a **fictitious weather agent application** that provides weather forecasts, alerts, and location-based services. This consistent example context helps demonstrate how the commands work without being tied to any specific real project.

## Commands

### `/bug` - TDD Bug Fixing
Guides you through fixing bugs using Test-Driven Development methodology with explicit user interaction points.

**Usage:** `/bug <description>`

**Process:**
1. **Research & Planning** - Reproduce the bug and identify root cause
2. **Write Failing Test** - Create a test that demonstrates the bug
3. **Implement Fix** - Write minimal code to make the test pass
4. **Refactor** (optional) - Clean up code while keeping tests green

**Example:** `/bug The weather forecast command throws KeyError when API response is missing temperature data`

### `/capture_need` - Capture Future Work
Quickly capture needs, ideas, bugs, or changes that should be addressed in future Claude Code sessions.

**Usage:** `/capture_need <name> '<description>'`

**Creates:** Draft specification in `specs/drafts/` with context from current session

**Example:** `/capture_need add_location_search 'Implement search functionality to find weather data by city name or coordinates'`

### `/spec` - Create Feature Specifications
Creates comprehensive specifications for new features following your project's standards.

**Usage:** `/spec <feature_name> "<brief_description>"`

**Creates:** Detailed specification file in `specs/` with:
- Overview & objectives
- Current state analysis
- Architecture design
- Integration strategy
- Acceptance criteria

**Example:** `/spec weather_alerts_system "Enable automated weather alerts based on location and user preferences"`

### `/spec_review` - Review Specifications
Reviews specification files for simplification opportunities, pythonic patterns, and architectural alignment.

**Usage:** `/spec_review @<spec_path>`

**Provides:**
- Simplification opportunities
- Pythonic improvements
- Code reuse opportunities
- Implementation questions
- Library recommendations

**Example:** `/spec_review @specs/2025-01-08_weather_api_integration.md`

### `/spec-tests` - Test Strategy Design
Writes comprehensive test specifications for existing spec files using TDD principles.

**Usage:** `/spec-tests @<spec-file> [instructions]`

**Creates:**
- Test strategy overview
- Unit and integration test plans
- Edge case identification
- Mock and fixture requirements

**Example:** `/spec-tests @specs/weather_api_integration.md "Focus on edge cases for notification handling"`

## Installation

1. Place these `.md` files in your Claude Code commands directory
2. The commands will become available as custom slash commands in your Claude Code sessions
3. Use tab completion or type the command name to see available options

## Benefits

- **Structured Workflows** - Each command provides a clear, step-by-step process
- **User Control** - Explicit interaction points ensure you maintain oversight
- **Quality Assurance** - Built-in testing and review processes
- **Documentation** - Automatically creates specifications and test plans
- **Consistency** - Standardized approaches across your development team
