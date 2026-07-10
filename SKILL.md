---
name: project-analysis
description: Analyze any software project/codebase and generate a comprehensive Markdown report. The skill automatically discovers what file types, frameworks, databases, APIs, and technologies are present — without any assumptions. Use this whenever someone says "analyze this project", "review this codebase", "generate a project report", "what does this project do", "audit this repo", or uploads/points to any project folder.
---

# Project Analysis Skill

Analyze any software project and produce a comprehensive Markdown report. You never assume anything about the project upfront — you investigate the actual project folder and discover everything from scratch.

## Core Principle

**Discover, don't assume.** Scan the actual project files first. Then report exactly what you find — what file types exist, what technologies are used, what databases are connected, what APIs are present. If something is not found, say "Not found" rather than guessing.

---

## Step 1 — Scan the Project

First, scan the entire project folder to discover what's actually there:

```
- List all folders and subfolders
- List all files grouped by their extension
- Read any README or documentation file
- Read any configuration or environment files
- Read the entry point file(s)
```

From this scan, build a complete picture:
- What file types/extensions exist in this project?
- How many files of each type?
- What is the folder structure?
- What are the main entry points?

Do NOT proceed to writing the report until this scan is complete.

---

## Step 2 — Investigate Each Area

Go through each area below. Base every finding on actual files and content you read — never fill in from assumptions.

### Project Overview
- What is this project?
- What type of project is it? (discover from the code itself — web app, mobile app, API, ML pipeline, CLI tool, library, etc.)
- What language(s) and file types does it use? (list exactly what you found in the scan)
- How big is it? (number of files, folders, approximate lines of code)

### Purpose
- What problem does this project solve?
- Who is it for?
- Base this on: README content, folder/file names, route names, UI text, model names, CLI help text, comments in code

### Technologies & Frameworks Used
- List every technology, framework, and library actually found in the project
- Show evidence for each (where you found it — which file, which import, which config)
- Do NOT list technologies that aren't present

### Architecture
- How is the project structured?
- What are the main components and how do they relate?
- What is the data flow?
- Describe the architectural style based on what you actually see

### Features & Functionality
- What can this project actually do?
- List every feature/function found — from routes, UI screens, CLI commands, public functions, or modules

### File Types Present
- List every file extension found in the project
- Group them by category (source code, config, data, assets, docs, etc.)
- For each type, explain what role those files play in this project

### Database Details
- Is there a database? (look for connection strings, ORM models, schema files, migration files, DB config)
- If yes: what type? what are the main tables/collections/models? how is it connected?
- If no database found: state "No database found"

### API Analysis
- Are there APIs in this project? (look for route definitions, endpoint decorators, API client calls, API keys in config)
- If yes: list every endpoint/method found with its purpose
- Are external APIs being called? List them
- If no API found: state "No API found"

### Security Implementation
- How is authentication handled? (look in the actual code)
- Are there any hardcoded secrets or API keys? (flag with file reference)
- How are inputs validated?
- Are environment variables used for sensitive config?
- Flag any specific security concerns found with exact file references

### Code Structure & Design Patterns
- How is the code organized?
- What patterns are actually used? (only name patterns you can point to with a real example in the code)
- What is the code quality like? (consistency, duplication, dead code, naming)

### Dependencies
- List every dependency actually declared in the project (from whatever dependency file exists)
- Separate runtime from development dependencies
- Note the dependency management approach used

### Build & Deployment
- How is the project built and run? (from scripts, config files, Dockerfiles, CI configs — whatever actually exists)
- Is there containerization? CI/CD? Hosting config?
- If none found: state "No build/deployment config found"

### Strengths
- List genuine strengths based on actual code evidence
- Never write generic praise — every point must reference something specific found in the project

### Issues & Improvement Suggestions
- List real issues found, ranked by severity
- Give specific, actionable suggestions tied to what was actually found
- Security issues go first

---

## Step 3 — Write the Report

Save the report as `<project-name>-analysis-report.md`.

Structure:
```
# <Project Name> — Analysis Report

## 1. Project Overview
## 2. Purpose
## 3. Technologies & Frameworks Used
## 4. Architecture
## 5. Features & Functionality
## 6. File Types Present
## 7. Database Details
## 8. API Analysis
## 9. Security Implementation
## 10. Code Structure & Design Patterns
## 11. Dependencies
## 12. Build & Deployment
## 13. Strengths
## 14. Issues & Improvement Suggestions
```

Every section must contain real findings from the actual project. If a section has nothing (e.g. no database, no API), write "Not found in this project" — never leave a section empty or filled with generic text.
