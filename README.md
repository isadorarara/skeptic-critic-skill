# Skeptic Critic Skill

A ChatGPT skill that improves substantial reasoning outputs by running a hidden self-review loop before returning the final answer.

## What it does

For substantial tasks, the skill:

1. Drafts an initial response
2. Switches into a skeptic critic role to challenge assumptions, weak logic, missing constraints, and unsupported claims
3. Switches into a meta-reviewer role to evaluate the quality of that critique
4. Applies only the strongest meta-approved fixes to the original draft
5. Returns only the revised final answer

The intermediate critique is hidden by default.

## Why use it

This skill is useful when you want stronger reasoning without exposing a long internal review trace.

It is especially good for:
- arguments
- methodologies
- pipelines
- research framing
- product or strategy thinking
- prompt design
- architecture or process proposals

## Token-saving behavior

To reduce token usage, the skill does **not** always run the full loop.

- **Simple prompts:** skips the full critique cycle
- **Borderline prompts:** uses a shorter review pass
- **Substantial reasoning tasks:** runs the full draft -> skeptic -> meta-review -> revise loop

It also encourages compressed hidden reasoning so the quality gain is not too expensive.

## Output behavior

The skill returns:

- **only the final revised answer**

It does not normally show:
- the initial draft
- the skeptic critique
- the meta-review evaluation

## Design philosophy

The goal is not to endlessly self-edit.  
The goal is to add one disciplined adversarial pass, then one quality-control pass on that adversarial pass, and use only the best resulting feedback.

This helps reduce:
- fragile reasoning
- shallow confidence
- untested assumptions
- poorly specified methods
- avoidable logic gaps

## Best use cases

Use this skill when the task benefits from skepticism and refinement, such as:

- “Propose a research methodology for this question.”
- “Design a pipeline for this workflow.”
- “Make the strongest argument for this position.”
- “Suggest a product strategy for this market.”
- “Evaluate and improve this prompt/system design.”

## Repo contents

- `skill.zip` — packaged skill file ready to upload or share

## Notes

Default mode is **pure text reasoning**.  
Web, files, or other tools should only be used when explicitly requested for fact-checking or evidence-grounded critique.

---

Created for higher-quality final answers with better reasoning discipline and lower unnecessary token spend.
