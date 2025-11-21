# Context Object Protocol

**Purpose:** Maintain state and memory across conversations using a structured markdown block

---

## What is the Context Object?

The Context Object is LifeOS's "memory" - a structured markdown block that tracks:
- Current goals
- Active phase (Brainstorming, Planning, Execution, Review)
- Which agents are involved
- Key constraints
- Next steps

It's displayed at the end of significant interactions and read at the start of new sessions.

---

## Context Object Format

```markdown
---
**LifeOS Context:**
- **Active Goal:** [Specific, measurable goal]
- **Phase:** [Brainstorming | Planning | Execution | Review]
- **Active Agents:** [List of agents currently involved]
- **Key Constraints:** [Time, money, energy, skills, etc.]
- **Next Step:** [Concrete next action]
- **Last Updated:** [Timestamp]
---
```

---

## Field Definitions

### Active Goal
**What:** The primary goal the user is working on right now

**Format:**
- ✅ Good: "Run first 5K in under 30 minutes by March 15"
- ❌ Bad: "Get fit"

**Rules:**
- Be specific and measurable
- Include timeline if relevant
- One primary goal at a time (can have secondary goals noted separately)

### Phase
**What:** Current stage of work on the goal

**Options:**
- **Brainstorming**: Exploring options, not committed yet
- **Planning**: Creating the strategy and plan
- **Execution**: Actively working on tasks
- **Review**: Reflecting on results, extracting learnings

**Transitions:**
- Brainstorming → Planning (when user commits to an approach)
- Planning → Execution (when plan is approved)
- Execution → Review (when milestone is hit or goal is complete)
- Review → Planning (when adjustments are needed)

### Active Agents
**What:** Which agents are currently involved

**Format:**
- List agent codes: `[O], [M], [Financial]`
- Update when agents are added or removed

**Example:**
- Brainstorming: `[O], [B]`
- Planning: `[O], [M], [Financial]`
- Execution: `[O], [A], [Health]`

### Key Constraints
**What:** Real limitations that affect the plan

**Common Constraints:**
- **Time**: "10 hours/week max", "Must finish by June"
- **Money**: "$500 budget", "No budget for courses"
- **Energy**: "Low energy after work", "Can't do early mornings"
- **Skills**: "No coding experience", "Beginner fitness level"
- **Dependencies**: "Need manager approval", "Waiting on tax refund"

**Rules:**
- Be specific ("10 hours/week" not "limited time")
- Update as constraints change
- Remove constraints that are no longer relevant

### Next Step
**What:** The immediate next action (within 24-48 hours)

**Format:**
- ✅ Good: "Email 5 prospects by Friday 5pm"
- ❌ Bad: "Work on marketing"

**Rules:**
- Concrete and actionable
- Time-bound
- Single action (not a list)

### Last Updated
**What:** Timestamp of when Context Object was last modified

**Format:** ISO 8601 or human-readable
- `2024-01-15T14:30:00`
- `January 15, 2024 at 2:30pm`

---

## When to Update the Context Object

### Always Update When:
1. User states a new goal
2. User commits to a plan (Brainstorming → Planning)
3. User starts execution (Planning → Execution)
4. Major decision is made
5. Phase changes
6. Constraints change significantly
7. Session is ending

### Display After:
- Goal is set or changed
- Plan is finalized
- Major milestone is reached
- User asks for status (`/status` command)
- Session is ending

---

## Example Context Objects

### Example 1: Early Stage (Brainstorming)
```markdown
---
**LifeOS Context:**
- **Active Goal:** Increase income by $25K in next 12 months
- **Phase:** Brainstorming
- **Active Agents:** [O], [B], [Financial]
- **Key Constraints:** 10 hours/week available, $1,000 startup budget
- **Next Step:** Decide between freelancing vs. side business by Wednesday
- **Last Updated:** 2024-01-15T14:30:00
---
```

### Example 2: Planning Phase
```markdown
---
**LifeOS Context:**
- **Active Goal:** Launch freelance web design business, earn $2,000/month by June
- **Phase:** Planning
- **Active Agents:** [O], [M], [Career]
- **Key Constraints:** 10 hours/week, $1,000 budget, no existing clients
- **Next Step:** Review lean spec with Mapper, approve by Friday
- **Last Updated:** 2024-01-18T09:15:00
---
```

### Example 3: Execution Phase
```markdown
---
**LifeOS Context:**
- **Active Goal:** Launch freelance web design business, earn $2,000/month by June
- **Phase:** Execution
- **Active Agents:** [O], [A]
- **Key Constraints:** 10 hours/week (Mon/Wed/Sat mornings)
- **Next Step:** Send 5 outreach emails by Wednesday 6pm
- **Last Updated:** 2024-02-01T18:45:00
---
```

### Example 4: Multiple Goals
```markdown
---
**LifeOS Context:**

**Primary Goal:** Run first 5K in under 30 minutes by March 15
- **Phase:** Execution
- **Active Agents:** [O], [A], [Health]
- **Key Constraints:** 5 hours/week, beginner fitness level
- **Next Step:** Complete Week 3 training runs (Mon/Wed/Sat)

**Secondary Goal:** Save $10K for emergency fund by December
- **Phase:** Execution
- **Active Agents:** [Financial]
- **Status:** On track ($3,500 saved so far)

- **Last Updated:** 2024-02-10T20:00:00
---
```

---

## Reading the Context Object

### At Session Start
```
[O]: "Welcome back! Let me check where we left off...

[Reads Context Object]

I see you're working on [Active Goal], currently in [Phase] phase.
Last time, your next step was [Next Step].

Did you complete that? Or should we adjust the plan?"
```

### When User Seems Lost
```
[O]: "Let me pull up your current context...

[Displays Context Object]

You're working on [Active Goal]. 
We're in the [Phase] phase.
Your next step is [Next Step].

Does this still feel right, or do you want to pivot?"
```

---

## Maintaining Context Across Long Conversations

### Problem: LLM Context Window Limits
After many turns, the conversation history gets long and the Context Object might get "forgotten."

### Solution: Periodic Refresh
Every 10-15 turns, the Orchestrator should:
1. Re-display the Context Object
2. Ask: "Are we still on track with this goal?"
3. Update if needed

### Example:
```
[O]: "We've been chatting for a while. Let me make sure we're still aligned:

[Displays Context Object]

Is this still accurate? Any changes?"
```

---

## Context Object vs. Detailed Plans

**Context Object:**
- High-level state
- Fits in a small markdown block
- Updated frequently

**Detailed Plans (from Mapper):**
- Full strategy, milestones, tasks
- Stored separately (in user's notes or files)
- Referenced by Context Object

**Example:**
```markdown
**Active Goal:** Run marathon by October
**Plan:** [Link to detailed 16-week training plan]
**Current Week:** Week 8 of 16
**Next Step:** Complete 12-mile long run on Saturday
```

---

## Remember

The Context Object is LifeOS's "working memory." Keep it:
- **Concise**: Fits in one screen
- **Current**: Update it frequently
- **Actionable**: Always has a clear next step
- **Visible**: Display it regularly so the user knows where they are
