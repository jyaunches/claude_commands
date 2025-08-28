---
name: scrub-examples
description: Analyze git changes and update examples to align with the weather agent context
---

# Scrub Examples Command

Updates examples in modified Claude command files to align with the weather agent application context defined in README.md.

## Process

1. **Identify Modified Files**: Check git status for modified command files (*.md)
2. **Analyze Changes**: Review the diffs to understand what's been added/changed
3. **Update Examples**: Replace any non-weather related examples with weather agent equivalents
4. **Maintain Consistency**: Ensure all examples follow the pattern established in README.md

## Weather Agent Context

Examples should reference:
- Weather forecasts and data retrieval
- Temperature/precipitation alerts
- Location-based services
- API integrations for weather data
- User notification preferences
- Historical weather tracking
- Storm warnings and alerts

## Example Transformations

### Before:
```
/bug User authentication fails when session expires
```

### After:
```
/bug The weather forecast command throws KeyError when API response is missing temperature data
```

## Execution Steps

1. Run `git status` to find modified files
2. Run `git diff` on each modified .md file
3. Identify examples that don't align with weather context
4. Generate appropriate weather-related replacements
5. Apply edits to align examples
6. Show summary of changes made

## Usage

```
/scrub-examples
```

This will automatically:
- Find all modified command files
- Update their examples to weather agent context
- Preserve the command functionality while updating examples