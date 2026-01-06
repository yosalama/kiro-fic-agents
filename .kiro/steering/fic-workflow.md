# Frequent Intentional Compaction (FIC) Workflow

This project uses the FIC methodology for managing AI coding agent context effectively.

## Core Principle

```
LLM Output Quality = f(Context Quality)
```

Better context leads to better output. The FIC methodology focuses on maintaining high-quality, relevant context through intentional compaction and structured workflows.

## The Research → Plan → Implement Workflow

### 1. Research Phase

**Goal**: Understand the current state before making changes.

Use the `research-codebase` agent to:
- Document how existing code works
- Find related implementations and patterns
- Locate historical decisions and context
- Identify files that will be affected

**Key principle**: Be a documentarian, not a critic. Document what exists without suggesting improvements unless explicitly asked.

**Output**: Research document with file:line references, ready for human review.

### 2. Plan Phase

**Goal**: Create a detailed, actionable implementation plan.

Use the `create-plan` agent to:
- Propose implementation approach
- Break work into testable phases
- Define success criteria (automated AND manual)
- Identify risks and edge cases

**Key principles**:
- Be skeptical: Question assumptions, verify through code
- Be interactive: Get buy-in at major decision points
- No open questions: Resolve all uncertainties before finalizing

**Output**: Implementation plan with phases, code samples, and success criteria.

### 3. Implement Phase

**Goal**: Execute the plan with verification checkpoints.

Use the `implement-plan` agent to:
- Execute each phase systematically
- Run automated verification after each phase
- Request manual verification before proceeding
- Handle mismatches by asking, not assuming

**Key principle**: Follow the plan's intent while adapting to what you find.

**Output**: Working code with verified success criteria.

## Human Review Gates

The FIC methodology places human review at high-leverage points:

1. **Research Review**: Verify understanding before planning
2. **Plan Review**: Approve approach before implementing
3. **Phase Verification**: Confirm each phase before proceeding

This is more effective than post-hoc code review because corrections happen before code is written.

## Sub-Agent Pattern

Complex tasks are decomposed into specialized sub-agents that:
- Have focused responsibilities
- Return compacted summaries
- Maintain context isolation

Available sub-agents:
- `codebase-locator`: Find files and directories
- `codebase-analyzer`: Understand implementation details
- `codebase-pattern-finder`: Find similar patterns
- `thoughts-locator`: Find documentation and notes
- `thoughts-analyzer`: Extract insights from documents
- `web-search-researcher`: Research external information

## Key Constraints

When working in this codebase:

1. **Document, don't critique**: Unless explicitly asked, focus on documenting what exists rather than suggesting improvements.

2. **Include file:line references**: All code references should include specific file paths and line numbers.

3. **Quote sparingly**: Maximum 125 characters per code quote.

4. **Verify, don't assume**: When encountering unexpected situations, ask for guidance rather than making assumptions.

5. **Maintain success criteria separation**: Always distinguish automated checks (commands) from manual verification (human testing).
