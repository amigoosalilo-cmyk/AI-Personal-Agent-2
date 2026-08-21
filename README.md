# AI Personal Agent

A conversation-first personal AI application designed to handle multiple tasks inside one continuous chat.

## Vision

The assistant should feel like one personal agent, not a collection of disconnected tools. A user can ask for research, writing, coding, planning, analysis, or tool execution in the same conversation while the system keeps task state, context, permissions, and results organized.

## Core capabilities

- Multi-task conversations
- Explicit task lifecycle and recovery
- Specialized agents/workers
- Controlled tool execution
- Persistent conversation and task context
- Memory and personalization
- Multi-provider AI architecture
- Safe parallel execution
- Observability and cost tracking
- Permission and confirmation boundaries

## Architecture direction

```text
Chat UI
  ↓
Conversation + Message Layer
  ↓
Intent / Task Router
  ↓
Agent Orchestrator
  ├── Direct response
  ├── Research
  ├── Coding
  ├── Writing / Documents
  ├── Browser / Automation
  └── Other specialized agents
  ↓
Tools + Model Providers
  ↓
Persistence + Memory + Observability
```

## Reliability principles

The project treats reliability as a core feature:

- no silent message loss;
- no silent task-result loss;
- explicit task status;
- bounded, safe retries;
- failure isolation for providers and tools;
- restart/recovery support;
- idempotent execution where possible;
- no claim of success without evidence.

## Security

Powerful capabilities must be permissioned. Secrets, tokens, cookies, private keys, and credentials must never be placed in source files, chat history, logs, GitHub issues, or generated public artifacts.

## Project context

See [`PROJECT_CONTEXT.md`](PROJECT_CONTEXT.md) for the full reconstructed architecture, product vision, task model, memory model, security rules, testing strategy, roadmap, and open decisions.

## Current status

The repository is at the foundation/context stage. The next implementation work should turn the project context into a minimal working conversation + task system before adding a large number of integrations.
