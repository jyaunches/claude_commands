# Claude Code Commands

My personal collection of custom commands for Claude Code.

## Example Context

All examples in these commands are derived from a **fictitious weather agent application** that provides weather forecasts, alerts, and location-based services. This demonstrates how the commands work without being tied to any specific real project.

## Commands

| Command | Description                                                                                                                                                                                                                                                                                                                                         | Usage | Example |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------|---------|
| **`/bug`** | TDD Bug Fixing - Guides you through fixing bugs using Test-Driven Development methodology with explicit user interaction points. Process:<br>1) Research & Planning<br>2) Write Failing Test<br>3) Implement Fix<br>4) Refactor (optional)                                                                                                          | `/bug <description>` | `/bug The weather forecast command throws KeyError when API response is missing temperature data` |
| **`/capture_need`** | Capture Future Work - Quickly capture needs, ideas, bugs, or changes that should be addressed in future Claude Code sessions.                                                                                                                                                                                                                       | `/capture_need <name> '<description>'` | `/capture_need add_location_search 'Implement search functionality to find weather data by city name or coordinates'` |
| **`/spec`** | Create Feature Specifications - Creates comprehensive specifications for new features following your project's standards.                                                                                                                                                                                                                           | `/spec <feature_name> "<brief_description>"` | `/spec weather_alerts_system "Enable automated weather alerts based on location and user preferences"` |
| **`/spec_review`** | Review Specifications - Reviews specification files before implementation for overcomplication or other issues you tend to see in generated code.                                                                                                                                                                                                   | `/spec_review @<spec_path>` | `/spec_review @specs/2025-01-08_weather_api_integration.md` |
| **`/spec-tests`** | Test Strategy Design - Following creation of spec, this creates a spec dedicated completely to the test strategy for that feature. | `/spec-tests @<spec-file> [instructions]` | `/spec-tests @specs/weather_api_integration.md "Focus on edge cases for notification handling"` |

## Installation (should you want to try them out!)

1. Place these `.md` files in your Claude Code commands directory
2. The commands will become available as custom slash commands in your Claude Code sessions
3. Use tab completion or type the command name to see available options

