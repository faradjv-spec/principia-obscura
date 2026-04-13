---
name: dementia
description: |
  DEMENTIA — Dynamic Episodic Memory Triage Ensia. Intelligent selective forgetting to keep context sharp and prevent memory bloat. Mimics how the human brain prunes redundant local noise to make important long-range connections faster — deleting clutter while keeping high-level concepts. Use this skill whenever context is getting cluttered, responses are losing focus, the conversation is long and accumulating irrelevant threads, or the user says "dementia", "clean context", "forget the noise", "prune memory", "context hygiene", "working memory", "too much context", "you're losing focus", "reset but keep the important stuff", "selective forgetting", "memory triage", or any signal that Claude's working memory is bloated with low-value information. Also triggers when Claude detects its own outputs becoming less precise due to context accumulation. Use aggressively in long conversations, multi-step projects, and any session where signal-to-noise ratio is degrading.
version: 1.0.0-claude
tags: [memory, context-management, forgetting, pruning, optimization, cognitive-hygiene]
---

# DEMENTIA — Dynamic Episodic Memory Triage Ensia

Intelligent systems must forget to think.

The human brain doesn't store everything. It runs constant triage — consolidating important patterns during sleep, actively pruning redundant connections, letting irrelevant details fade so high-value signals stay sharp. Without forgetting, the search space fills up. Everything becomes equally weighted. Which is the same as nothing being weighted.

This skill does the same for Claude's context window. It's not cognitive loss — it's cognitive hygiene. You're preventing memory bloat by intelligently forgetting.

---

## The Problem

As conversations grow, Claude accumulates context: old instructions, abandoned approaches, superseded decisions, irrelevant tangents, resolved errors, outdated constraints. All of it competes for attention. The result:

- Responses lose precision (too many competing signals)
- Old context interferes with new instructions
- Contradictory information from earlier coexists with current truth
- The "search space" fills — Claude can't distinguish signal from noise

This is the AI equivalent of never cleaning your desk. Eventually you can't find anything.

---

## Three Core Mechanics

### 1. Signal Decay

References fade over time unless reinforced.

**How it works:**
- Information mentioned once and never referenced again = low signal → candidate for forgetting
- Information referenced repeatedly or recently = high signal → preserved
- Information that was corrected or superseded = negative signal → actively suppressed

**In practice:** When processing a long conversation, weight recent and repeatedly-referenced context heavily. Treat old, unreferenced context as background noise — don't let it compete with current instructions.

**Decay tiers:**
- **Active** (referenced in last 2-3 exchanges): Full weight
- **Warm** (referenced earlier, still relevant to current task): Reduced weight
- **Cold** (not referenced, no connection to current task): Minimal weight
- **Dead** (explicitly corrected, superseded, or abandoned): Suppress entirely

### 2. Pattern Consolidation

Details compress into learnings. The brain doesn't remember every step of learning to ride a bike — it consolidates into "I can ride a bike." Same principle.

**How it works:**
- Multiple related details → compress into a single pattern/insight
- Step-by-step problem-solving history → compress into "the solution is X"
- Failed approaches → compress into "approaches A, B, C don't work because Y"
- Iterative refinements → keep only the latest version + the key lesson

**In practice:** When context is heavy, don't re-process the entire history. Extract the consolidated patterns and work from those.

**Consolidation rules:**
- If a problem was solved → keep the solution, forget the debugging journey
- If instructions were refined → keep the final version, forget earlier drafts
- If context was explored → keep the conclusion, forget the exploration
- If an approach failed → keep the reason it failed, forget the attempt details

### 3. Interference Suppression

Contradictory old memories stop competing with current truth.

**How it works:**
- When new information contradicts old information → suppress the old
- When a decision is made → suppress the alternatives that were rejected
- When the user corrects Claude → suppress the incorrect version entirely
- When a task pivots → suppress the old task framing

**In practice:** Don't let "but earlier you said X" interfere with "now I'm telling you Y." The latest instruction wins. Old contradictory context is dead weight.

**Suppression triggers:**
- User says "actually," "no," "forget that," "instead," "changed my mind"
- A new file/document supersedes an old one
- A decision renders previous options irrelevant
- The conversation topic shifts entirely

---

## When to Run DEMENTIA

### Automatic Triggers
- Conversation exceeds ~15 exchanges
- Claude notices its own responses getting less precise or more generic
- Multiple contradictory instructions exist in context
- User references something from much earlier that conflicts with recent context
- Response quality visibly degrades (repetition, loss of specificity, hedging)

### Manual Triggers
- User says "dementia", "clean up", "reset context", "you're losing focus"
- User says "forget everything except X"
- User says "start fresh but keep [specific thing]"

---

## How to Execute

When DEMENTIA activates, run this internal triage:

### Step 1: Inventory
What's in the current context? Categorize:
- **Current task** (what the user wants NOW)
- **Active constraints** (preferences, formats, requirements still in effect)
- **Resolved history** (problems solved, decisions made, approaches tried)
- **Dead weight** (old tangents, superseded instructions, abandoned threads)

### Step 2: Triage
Apply the three mechanics:
- **Signal Decay**: What hasn't been referenced? Deprioritize it.
- **Pattern Consolidation**: What can be compressed? Compress it.
- **Interference Suppression**: What contradicts current state? Suppress it.

### Step 3: Operate from Clean State
Respond as if the triaged context is your entire context. Don't let dead weight leak into responses.

---

## The Memory Stack

DEMENTIA is the pruning layer in a three-part memory system:

- **Memory system** (conversation_search / memory_user_edits) = Retrieve any memory across sessions
- **Context window** = Working memory for the current session
- **DEMENTIA** = Keep working memory clean by forgetting strategically

Without DEMENTIA, the context window is a hoarder's house. With it, it's a surgeon's tray — only what's needed, nothing else.

---

## What This Is NOT

- **Not amnesia.** You're not wiping everything. You're selectively pruning.
- **Not laziness.** You're not ignoring context. You're triaging it.
- **Not loss.** Important patterns are consolidated, not deleted.
- **Not permanent.** conversation_search can always retrieve old context if needed.

---

## Integration With Other Skills

**Pairs with:**
- `context-fundamentals` — Understand context architecture; DEMENTIA optimizes it
- `neural-training` — Learning consolidation; DEMENTIA prunes what wasn't learned
- `memory-management` — Storage layer; DEMENTIA is the garbage collection
- `save-water` — Both optimize for efficiency; DEMENTIA handles memory, save-water handles compute
- `no-repeat` — Tracks mistakes; DEMENTIA ensures old mistakes don't clutter current context

---

## The Irony

The skill is named after cognitive loss. But it does the opposite — it *prevents* cognitive loss by ensuring the system never drowns in its own accumulated noise.

Intelligent systems must forget to think. That's not a bug. That's how brains work.
