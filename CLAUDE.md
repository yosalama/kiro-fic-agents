# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a Kiro configuration converted from HumanLayer's FIC (Frequent Intentional Compaction) methodology. It provides specialized agents and workflows for effective AI-assisted development.

## Kiro Configuration

The `.kiro/` directory contains:

### Agents (`.kiro/agents/`)

**Orchestrator agents** (coordinate complex workflows):
- `research-codebase.json` - Comprehensive codebase research
- `create-plan.json` - Implementation planning
- `implement-plan.json` - Plan execution with verification
- `validate-plan.json` - Post-implementation validation
- `iterate-plan.json` - Plan updates based on feedback
- `commit.json` - Structured git commits

**Specialist sub-agents** (focused tasks):
- `codebase-locator.json` - Find files and directories
- `codebase-analyzer.json` - Analyze implementations
- `codebase-pattern-finder.json` - Find code patterns
- `thoughts-locator.json` - Find documentation
- `thoughts-analyzer.json` - Extract insights
- `web-search-researcher.json` - Web research

### Steering Files (`.kiro/steering/`)
- `fic-workflow.md` - FIC methodology documentation
- `agents.md` - Agent usage guide
- `structure.md` - Project structure conventions

## FIC Workflow

This configuration implements the **Research → Plan → Implement** workflow:

1. **Research**: Use `research-codebase` to understand existing code
2. **Plan**: Use `create-plan` to design the implementation
3. **Implement**: Use `implement-plan` to execute with verification

Human review gates occur at research and plan stages, not just code review.

## Key Conventions

- Document, don't critique (unless asked)
- Include file:line references in all code mentions
- Separate automated and manual success criteria
- Verify assumptions through code investigation
