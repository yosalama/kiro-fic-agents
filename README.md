# Kiro Agents Quick Start

Pre-configured AI agents that help you research, plan, and build code systematically. Instead of chatting back and forth, these agents follow proven workflows that produce better results.

## Getting Started

In any Kiro chat, type:
```
/agent swap research-codebase
```

Then describe what you want to understand. That's it.

---

## When to Use What

### "I need to understand this code"
```
/agent swap research-codebase
```
Researches the codebase and produces a document with file references. Great for onboarding to a new area or investigating how something works.

**Example prompt:** "How does authentication work in this project?"

---

### "I need to plan a feature or fix"
```
/agent swap create-plan
```
Creates a detailed implementation plan with phases, code samples, and test criteria. The agent will ask you questions to clarify requirements.

**Example prompt:** "I need to add rate limiting to the API endpoints"

---

### "I have a plan, let's build it"
```
/agent swap implement-plan
```
Executes an implementation plan phase by phase, running tests and asking for verification at each step.

**Example prompt:** "Implement the plan at thoughts/shared/plans/2024-01-15-rate-limiting.md"

---

## Why This Works Better

**Without agents:**
```
You: "Add rate limiting"
AI: *writes code immediately*
You: "Wait, that's not how our API works"
AI: *rewrites everything*
You: "Actually we already have a rate limiter util..."
AI: *rewrites again*
```

**With agents:**
```
You: /agent swap create-plan
You: "Add rate limiting"
Agent: "I found your existing rate limiter at src/utils/rateLimit.ts.
        Your API uses Express middleware. Here are two approaches...
        Which do you prefer?"
You: "Option 1"
Agent: *creates detailed plan for your review*
You: /agent swap implement-plan
Agent: *builds it correctly the first time*
```

---

## Tips

1. **Start with research** if you're unfamiliar with the code area
2. **Let the agent ask questions** - it will clarify before assuming
3. **Review plans before implementing** - catch issues early, not in code review
4. **Be specific** - "add logging to auth" beats "improve the code"

---

## All Available Agents

| Agent | Use When |
|-------|----------|
| `research-codebase` | Understanding existing code |
| `create-plan` | Planning new features or changes |
| `implement-plan` | Executing an approved plan |
| `validate-plan` | Verifying implementation matches plan |
| `iterate-plan` | Updating a plan based on feedback |
| `commit` | Creating well-structured commits |

*The other agents you'll see (like `codebase-analyzer`) are specialists that get called automatically—you don't need to use them directly. See [.kiro/steering/agents.md](.kiro/steering/agents.md) for details.*

List all agents: `/agent list`

---

## Appendix: Background & Theory

> **You don't need to read this to use the agents above.** This section is for those curious about where this approach came from.

### Origin

These agents are converted from [HumanLayer's `.claude` configuration](https://github.com/humanlayer/humanlayer/tree/main/.claude), which implements their **FIC (Frequent Intentional Compaction)** methodology for AI-assisted development.

### The Core Idea

```
LLM Output Quality = f(Context Quality)
```

The better the context you give an AI, the better the output. Instead of dumping everything into one long conversation, FIC uses:

1. **Specialized sub-agents** that focus on one task and return summarized findings
2. **Research → Plan → Implement** workflow that builds understanding incrementally
3. **Human review gates** at research and planning stages (not just code review)

The insight is that reviewing a *plan* before coding starts is higher leverage than reviewing code after it's written. Catching "wrong approach" early beats fixing it later.

### Further Reading

- [FIC Methodology Overview](https://deepwiki.com/humanlayer/advanced-context-engineering-for-coding-agents/1-overview) - The theory behind context engineering
- [HumanLayer GitHub](https://github.com/humanlayer/humanlayer) - Original `.claude` configuration
- [Kiro Documentation](https://kiro.dev/docs/) - Kiro CLI reference
- [Research-Plan-Implement Workflow](https://deepwiki.com/humanlayer/advanced-context-engineering-for-coding-agents/3-the-research-plan-implement-workflow) - Deep dive on the workflow
