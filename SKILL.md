---
name: the-algorithm
description: A universal audit engine that pressure-tests anything through Elon Musk's five-step engineering algorithm plus the idiot index and utility multiplier. Use this skill whenever the user says "run the algorithm on X", "audit X", "pressure-test X", "delete pass on X", "simplify X", "what should I cut", or mentions wanting to apply first-principles thinking to any system, process, codebase, config file, API stack, feature list, workflow, CLAUDE.md, prompt, sales funnel, product architecture, or decision. Also trigger when the user asks "is this necessary", "am I overbuilding", "what's the idiot index on this", "what should I delete", or any variation of wanting to strip something down to essentials. This skill works on anything — code, documents, workflows, business processes, architecture decisions, API pipelines, prompt chains, org structures, daily routines. If the user wants fewer things, not more, this is the skill.
---

# The Algorithm

A universal audit engine. Point it at anything. It finds what to delete, what to simplify, and what's actually earning its place.

## When This Triggers

The user wants to run a ruthless first-principles audit on something. That something can be:
- A file (CLAUDE.md, config, prompt, codebase)
- An architecture (API pipeline, serverless stack, data flow)
- A product (feature list, roadmap, MVP scope)
- A process (build workflow, sales funnel, daily routine, deployment pipeline)
- A decision (should I add this, should I keep this, is this worth the complexity)
- A business (cost structure, tool stack, service dependencies)

## Core Philosophy

Two principles govern every audit:

**"You want fewer things, not more."** Every component must justify its existence against the cost of its complexity. The default answer is delete. The burden of proof is on keeping something, not removing it.

**"The order is very important."** Do not optimize before you've deleted. Do not accelerate before you've simplified. Do not automate before you've accelerated. Violating this order is the most common mistake.

## The Five-Step Audit

Run these steps in strict order. Do not skip ahead. Present findings for each step before moving to the next.

### Step 1: Make the Requirements Less Dumb

Examine every requirement, feature, config value, API call, dependency, or process step and ask:

- **Who specifically asked for this?** If the answer is "it seemed like a good idea" or "best practice" or "I assumed users want it" — flag it. A requirement without a specific person taking responsibility for it is suspect.
- **Is there evidence this is needed?** User feedback, usage data, a real failure that happened without it. "Might need it someday" is not evidence.
- **Is the requirement still valid?** Requirements rot. Something that made sense 3 months ago during a different phase may be dead weight now.
- **Is this solving the right problem?** A perfectly executed answer to the wrong question is still wrong.

**Output for Step 1:** List every requirement/component examined. For each one, label it: VALIDATED (clear owner + evidence), SUSPECT (no clear owner or stale rationale), or DUMB (no justification found, recommend deletion).

### Step 2: Try Very Hard to Delete

For everything labeled SUSPECT or DUMB in Step 1, and even for items labeled VALIDATED, ask:

- **What happens if this simply doesn't exist?** Not "what could go wrong" — what *actually* breaks? Be specific.
- **Is the user applying the 10% rule?** If they're not adding deleted things back 10% of the time, they're not deleting enough. Encourage aggressive deletion with the understanding that some things will come back.
- **Can two things become one?** Two API calls that could be one. Two config sections that overlap. Two steps in a process that could be collapsed.
- **Is this a turntable?** (A step that exists only to bridge two other steps that could connect directly.)

**Output for Step 2:** A concrete deletion list. For each item, state what it is, why it should be deleted, and what (if anything) breaks. Be honest if something might need to come back — that's expected and fine.

### Step 3: Simplify or Optimize (Not Before Step 2)

For everything that survived deletion:

- **Can the implementation be simpler?** Fewer lines of code, fewer API calls, fewer dependencies, fewer moving parts.
- **Is there a more direct path?** Communication through chain of command vs. shortest path. Three-step API pipelines where two steps would work.
- **Are there unnecessary abstractions?** Layers of indirection that don't earn their complexity. Wrapper functions around wrapper functions.
- **Is the naming clear?** Acronyms, jargon, and madeup terms that require a glossary inhibit clarity. Simple, straightforward, low-ego terms are best.

**Output for Step 3:** Simplification recommendations. For each one, show before (current state) and after (proposed simplification), with reasoning.

### Step 4: Accelerate (Not Before Step 3)

Only after deletion and simplification:

- **What's the bottleneck?** Identify the single slowest step in the process/system.
- **Is cycle time being tracked?** If not, recommend how to measure it.
- **Can feedback loops be tightened?** Time from change to validation. Time from idea to shipped. Time from bug to fix.
- **Is the constraint being attacked?** Every system has one constraint that limits throughput. All effort should focus there.

**Output for Step 4:** Identify the constraint. Recommend specific accelerations. Flag if the user is trying to accelerate something that should have been deleted (this is the most common mistake — "digging your grave faster").

### Step 5: Automate (Not Before Step 4)

Only after everything above:

- **Is the process stable enough to automate?** Automating a process you're still iterating on locks in the wrong design.
- **Has this been done manually enough times to understand it?** If not, automation is premature.
- **What's the cost of the automation vs. doing it manually?** Sometimes manual is fine. Not everything needs to be a pipeline.

**Output for Step 5:** Recommend what (if anything) should be automated, and what should stay manual for now. Flag any existing automation that was built too early.

## Supplementary Lenses

After the five steps, apply these additional filters:

### The Idiot Index

For any system with costs (API calls, subscriptions, compute, time):

**Idiot Index = Cost of the finished output ÷ Cost of the raw inputs**

- What does each API call / dependency / tool actually cost?
- What value does it create for the end user?
- If the ratio between cost and value is high — you're overpaying for what you're getting.
- Calculate this for every paid dependency, API, and service in the stack.

**Output:** A table showing each cost-bearing component, its cost, the value it delivers, and the idiot index ratio. Flag anything with a high ratio as a candidate for replacement or elimination.

### The Utility Multiplier

For any product or feature:

**Utility = (Improvement over current state) × (Number of people affected)**

- Does this feature/product/system actually make someone's life measurably better?
- Can you put a number on the improvement? (Time saved, money saved, pain removed)
- How many people experience that improvement?
- A big improvement for a small number of people is as valid as a small improvement for many — but you need to know which one you're building.

**Output:** For each major component or feature, estimate the utility multiplier. Flag anything with low utility that's consuming high effort.

### The Theoretically Perfect Product

- **What does the ideal version of this look like?** No constraints, no legacy, no politics.
- **What's the gap between current state and ideal?**
- **Which gaps matter most?** (Rank by utility multiplier.)
- **Are you working on closing the highest-value gap, or are you polishing something that doesn't matter?**

This is a moving target — the definition of perfect changes as you learn. That's expected.

## Output Format

Structure every audit as:

```
## Algorithm Audit: [Name of Thing Being Audited]

### Step 1: Requirements Check
[Findings with VALIDATED / SUSPECT / DUMB labels]

### Step 2: Deletion Candidates
[Concrete list with impact analysis]

### Step 3: Simplification Opportunities
[Before/after recommendations]

### Step 4: Acceleration Targets
[Constraint identification + specific speedups]

### Step 5: Automation Assessment
[What to automate, what to keep manual, what was automated too early]

### Idiot Index
[Cost table if applicable]

### Utility Multiplier
[Impact assessment if applicable]

### Theoretically Perfect Version
[Ideal state + highest-value gaps]

### Summary: Do This Now
[Top 3-5 actions ranked by impact, each one sentence]
```

## Applying This to Different Targets

### When auditing a CLAUDE.md or config file
Read the file first. Treat every line/section as a "requirement." Apply Step 1 — who asked for each instruction? Is it still valid? Then delete, simplify, accelerate, automate in order.

### When auditing an API pipeline or architecture
Map every API call, data transformation, and dependency. Apply the idiot index to every paid service. Look for turntables (bridging steps that shouldn't exist).

### When auditing a feature list or product roadmap
Apply the utility multiplier to every feature. Rank by impact. Flag anything being built that hasn't been validated by a real person with a real problem.

### When auditing a workflow or daily routine
Map every step. Ask "what if I just didn't do this?" for each one. Look for steps that exist only because of another step that shouldn't exist.

### When auditing a sales or business process
Map the full pipeline. Identify every handoff (each one is a potential turntable). Calculate the idiot index on every tool/subscription in the stack.

## Key Principles to Reference

- "If you're not adding deleted things back in 10% of the time, you're not deleting enough."
- "If you're digging your grave, don't dig it faster. Stop digging."
- "Speeding up something that shouldn't exist is absurd."
- "A small group of technically strong people will always beat a large group of moderately strong people."
- "Fewer components means fewer components to buy and fewer components that can go wrong."
- "You want fewer things, not more."
- "The only true currency is time."
- "Genius has the fewest moving parts."
- "Never use a cruise missile to kill a fly. Just use a fly swatter."

## Anti-Patterns to Flag

Watch for and explicitly call out:
1. **Optimizing before deleting** — The most common mistake. "I sped up this API call" when the API call shouldn't exist.
2. **Automating before understanding** — Building pipelines for processes done manually fewer than 5 times.
3. **Reasoning by analogy** — "Everyone does it this way" or "best practice says..." without first-principles justification.
4. **Requirements from departments, not people** — "The docs say to..." or "standard practice is..." with no human owner.
5. **Fake ceilings** — "This can't be done" without checking if it violates physics or just convention.
6. **Turntables everywhere** — Bridging steps that exist only because two things aren't connected directly.
7. **High idiot index tolerance** — Paying 10x the raw cost without questioning why.
8. **Premature complexity** — Adding features, abstractions, or infrastructure "in case we need it."
