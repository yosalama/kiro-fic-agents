# Available Agents

This project includes specialized agents for the FIC (Frequent Intentional Compaction) workflow.

## Orchestrator Agents

These agents coordinate complex workflows:

### research-codebase
Conducts comprehensive codebase research using parallel sub-agents. Produces research documents with file:line references.

**Use when**: You need to understand how something works, find related code, or document existing implementations.

**Swap command**: `/agent swap research-codebase`

### create-plan
Creates detailed technical implementation plans through interactive research and iteration.

**Use when**: You need to plan a feature, fix, or refactor before implementing.

**Swap command**: `/agent swap create-plan`

### implement-plan
Implements technical plans phase by phase with verification checkpoints.

**Use when**: You have an approved implementation plan ready to execute.

**Swap command**: `/agent swap implement-plan`

### validate-plan
Validates that an implementation plan was correctly executed.

**Use when**: After implementing a plan to verify completeness and correctness.

**Swap command**: `/agent swap validate-plan`

### iterate-plan
Updates existing implementation plans based on feedback.

**Use when**: You need to modify an approved plan based on new information.

**Swap command**: `/agent swap iterate-plan`

### commit
Creates well-structured git commits with user oversight.

**Use when**: You need to commit changes with proper review and logical grouping.

**Swap command**: `/agent swap commit`

## Specialist Sub-Agents

These agents are spawned by orchestrators for focused tasks:

### codebase-locator
Finds files and directories relevant to specific features or tasks.

### codebase-analyzer
Analyzes implementation details, traces data flow, documents technical mechanisms.

### codebase-pattern-finder
Finds existing code patterns, implementations, and usage examples.

### thoughts-locator
Discovers relevant documents in thoughts/ or docs/ directories.

### thoughts-analyzer
Extracts high-value insights from research documents.

### web-search-researcher
Researches information from the web for modern documentation and best practices.

## Usage Pattern

1. Start with an orchestrator agent for your workflow
2. The orchestrator will spawn sub-agents as needed
3. Sub-agents return compacted summaries to the orchestrator
4. The orchestrator synthesizes results and presents to you

## Swapping Agents

To switch to a different agent:

```
/agent swap [agent-name]
```

To list available agents:

```
/agent list
```
