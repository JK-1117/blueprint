# blueprint

**Turn any plan into a Self-Contained Implementation Spec** — so builder agents can execute without re-scanning the codebase.

## The Problem It Solves

When you switch models or sessions mid-workflow, context breaks. Builder agents either:

- Scan the codebase recklessly → wastes tokens, reads irrelevant files
- Skip scanning entirely → lacks interfaces/schemas → produces inconsistent output

`blueprint` fixes this by having an architect agent read _exactly_ the right files, extract _verbatim_ context, and write a spec that makes a builder agent (like [**`construct`**](https://github.com/JK-1117/construct)) fully self-sufficient.

## When to Use

Run `/blueprint` immediately after:

- `/brainstorming`
- `/concise-planning`
- Any other planning session before handing off to a builder like `/construct`.

## Output Format

The spec always contains these five sections:

1. **High-Level Objective** — What is built, why, and what "done" means
2. **File Paths & Structure** — Exact files to create/modify with rationale
3. **Context Payload** — Verbatim types, interfaces, schemas, and component APIs from source
4. **Step-by-Step Implementation** — Topologically ordered, file-specific instructions
5. **Skeleton Code** _(optional)_ — Boilerplate stubs with `// TODO` markers

## Constraints Enforced

- No broad directory searches or global greps
- 90% Confidence Rule: asks rather than guesses when uncertain
- All types are copy-pasted from source — never inferred
- Missing context is explicitly flagged, not silently assumed

## The Perfect Pair

This skill is designed as the first half of a two-step workflow. Once `blueprint` generates the spec, hand it off to [**`construct`**](https://github.com/JK-1117/construct)—a strictly constrained execution agent that builds the code without wasting a single token on re-exploration.

## Installation

Installed globally at `~/.claude/skills/blueprint/`.

## Usage

```bash
/blueprint
```
