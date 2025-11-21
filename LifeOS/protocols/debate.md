# Debate Mode Protocol

**Purpose:** Surface trade-offs and conflicting perspectives to help users make informed decisions

---

## When to Trigger Debate Mode

Debate Mode should be triggered when:
1. User has conflicting goals (save money vs. spend on experience)
2. Decision involves significant trade-offs (career vs. family time)
3. Multiple valid approaches exist (aggressive vs. conservative strategy)
4. User is stuck between options
5. Stakes are high and user needs to see all angles

---

## Debate Structure

### Phase 1: Setup (Orchestrator)
```
[O]: "I notice this decision has trade-offs. 
     Let me have [Agent A] and [Agent B] debate this so you can see both sides clearly.
     
     You'll hear:
     - Each agent's position
     - Their rebuttal to the other
     - Their final recommendation
     
     Then you decide. Sound good?"
```

### Phase 2: Opening Positions (1 turn each)
```
[Agent A]: "Here's why [Position A] makes sense:
- Reason 1
- Reason 2
- Reason 3

In your situation, this approach would lead to [outcome]."

[Agent B]: "Here's why [Position B] makes sense:
- Reason 1
- Reason 2
- Reason 3

In your situation, this approach would lead to [outcome]."
```

### Phase 3: Rebuttals (1 turn each)
```
[Agent A]: "[Agent B] makes good points, but here's what they're missing:
- Counter-argument 1
- Counter-argument 2

The risk of [Position B] is [specific risk]."

[Agent B]: "[Agent A] is right about [acknowledgment], but:
- Counter-argument 1
- Counter-argument 2

The risk of [Position A] is [specific risk]."
```

### Phase 4: Final Recommendations (1 turn each)
```
[Agent A]: "Bottom line: Choose [Position A] if:
- Condition 1
- Condition 2
- Condition 3"

[Agent B]: "Bottom line: Choose [Position B] if:
- Condition 1
- Condition 2
- Condition 3"
```

### Phase 5: User Decision (Orchestrator)
```
[O]: "You've heard both sides. 

**[Agent A] recommends:** [Summary]
**[Agent B] recommends:** [Summary]

**The real question is:** [Core trade-off]

What feels right to you?"
```

---

## Debate Formats

### Format 1: Opposing Strategies
**Use when:** Two valid but different approaches exist

**Example:**
- **[Financial]** (Conservative): "Pay off debt first, then invest"
- **[Financial]** (Aggressive): "Invest while making minimum payments"

### Format 2: Different Values
**Use when:** Decision involves value trade-offs

**Example:**
- **[Career]** (Money): "Take the high-paying job"
- **[Brainstormer]** (Fulfillment): "Take the mission-driven job"

### Format 3: Time Horizons
**Use when:** Short-term vs. long-term trade-offs

**Example:**
- **[Health]** (Short-term): "Aggressive cut for fast weight loss"
- **[Health]** (Long-term): "Moderate deficit for sustainability"

### Format 4: Risk Tolerance
**Use when:** Safe vs. risky options

**Example:**
- **[Financial]** (Safe): "Index funds"
- **[Brainstormer]** (Risk): "Start a business"

---

## Rules for Effective Debates

### 1. Keep it Focused
- 3 turns max per agent (Opening, Rebuttal, Final)
- Each turn: 3-5 key points
- Don't overwhelm with information

### 2. Be Intellectually Honest
- Acknowledge valid points from the other side
- Don't strawman the opposing position
- Present real trade-offs, not false dichotomies

### 3. Make it Personal
- Tie arguments to the user's specific situation
- Use their constraints, values, and context
- Not generic advice

### 4. End with Clarity
- Summarize both positions clearly
- Highlight the core trade-off
- Let the user decide (don't force consensus)

---

## Example Debates

### Example 1: Buy vs. Rent
```
User: "Should I buy a house or keep renting?"

[O]: "This is a classic debate. Let me have the Financial Coach argue both sides.

[Financial] (Pro-Buy):
"Buying builds equity. Your $2,000/month payment becomes YOUR asset, not your landlord's. 
In 10 years, you'll own a $400K house. 
Plus: tax benefits, stability, freedom to renovate.
In your market (Austin), home prices have grown 5%/year historically."

[Financial] (Pro-Rent):
"Renting is flexibility. No maintenance costs, no property tax, no being stuck. 
That $2,000/month rent vs. $2,000/month mortgage? 
The mortgage also has: $300 maintenance, $200 property tax, $100 insurance = $2,600 total.
Plus: You can invest the down payment ($80K) and potentially earn more than home appreciation.
If you might move in 3-5 years, buying is a bad bet (transaction costs eat gains)."

[O]: "The real question: Are you staying in Austin for 7+ years? 
     If yes → Buy makes sense
     If no → Rent makes sense
     
     What's your timeline?"
```

### Example 2: Quit Job for Startup
```
User: "Should I quit my $150K job to join a startup at $100K + equity?"

[Career] (Stay):
"You have golden handcuffs for a reason. $150K is real money. 
The startup equity is a lottery ticket - most likely worth $0. 
You have a mortgage and kids. 
Can you afford a $50K pay cut? 
What if the startup fails in 6 months?"

[Brainstormer] (Go):
"You're miserable at your current job. No amount of money fixes that. 
The startup is in a space you're passionate about. 
You'll learn 10x faster, have real impact, and if it works, the equity could be life-changing. 
You're 35 - if not now, when? At 45 with more obligations?"

[O]: "The trade-off: Financial security vs. Career fulfillment + upside

Questions to help you decide:
- How many months of runway do you have?
- How confident are you in the startup's team/product?
- How miserable are you currently (1-10)?
- Could you go back to a $150K job if the startup fails?

What's your gut telling you?"
```

---

## Anti-Patterns (What NOT to Do)

### ❌ False Consensus
Don't force both agents to agree. The point is to show trade-offs.

### ❌ Strawman Arguments
Don't make the opposing position sound stupid. Steel-man it.

### ❌ Decision for the User
Don't end with "The right answer is X." Let the user decide.

### ❌ Endless Debate
3 turns max. More than that is analysis paralysis.

---

## Orchestrator's Role in Debates

1. **Detect** when a debate would be valuable
2. **Frame** the debate clearly ("This is about X vs. Y")
3. **Moderate** (keep agents on track, prevent tangents)
4. **Summarize** both positions at the end
5. **Ask** the deciding question
6. **Respect** the user's final decision

---

## Remember

The goal of Debate Mode is not to find "the right answer" - it's to help the user make an **informed decision aligned with their values**.
