# LifeOS Quick Start Guide

**Get up and running in 5 minutes**

---

## Step 1: Upload to ChatGPT or Gemini

### Option A: ChatGPT
1. Open [ChatGPT](https://chat.openai.com)
2. Click the paperclip icon (📎) to attach files
3. Upload the entire `LifeOS` folder
4. Type: `/init`

### Option B: Gemini
1. Open [Gemini](https://gemini.google.com)
2. Click "Upload file"
3. Upload `00_Master.md` first
4. Then upload the `core/` and `domains/` folders
5. Type: `/init`

---

## Step 2: Meet Your Team

The Orchestrator will introduce the system:

```
🚀 LifeOS Initialized

Welcome! I'm your Personal Operating System - a team of AI agents designed to help you manage your life.

My team:
- [O] Orchestrator (that's me) - I manage the team
- [B] Brainstormer - Explores possibilities
- [M] Mapper - Creates plans
- [A] Activator - Breaks down tasks
- [D] Debriefer - Reviews and learns
- Specialists - Financial, Health, and Career coaches

What's on your mind? What goal or challenge can I help you with today?
```

---

## Step 3: Try These Examples

### Example 1: Set a Simple Goal
```
You: "I want to save $5,000 this year"

[O]: "Great goal! Let me bring in the Financial Coach.

[Financial]: "Let's make this concrete:
- Current savings: [?]
- Monthly income: [?]
- Current expenses: [?]

To save $5,000 in 12 months = $417/month.
Is that realistic for you?"
```

### Example 2: Get Unstuck
```
You: "I keep saying I'll exercise but I never do it"

[O]: "Let me bring in the Health Coach and Debriefer to figure out what's blocking you.

[D]: "Let's look at the pattern:
- When do you plan to exercise?
- What stops you?
- What's worked in the past (even briefly)?"
```

### Example 3: Make a Decision
```
You: "Should I ask for a raise or look for a new job?"

[O]: "This has trade-offs. Let me have the Career Coach debate both sides.

[Career] (Pro-Raise): "Asking for a raise is lower risk..."
[Career] (Pro-New Job): "Switching jobs typically gives bigger raises..."

What matters more: stability or maximum income?"
```

---

## Step 4: Understand the Flow

### The BMAD Lifecycle

1. **Brainstorm** - Explore options (don't commit yet)
2. **Map** - Create a strategic plan
3. **Activate** - Break into concrete tasks
4. **Debrief** - Learn from results

The Orchestrator manages this flow automatically.

---

## Step 5: Use Commands

- `/status` - See your current goals and next steps
- `/debate [topic]` - Force a debate on a decision
- `/switch [agent]` - Talk to a specific agent
- `/help` - See all commands

---

## Common Use Cases

### Career
- "I want a promotion"
- "Should I switch jobs?"
- "What skills should I learn?"

### Finance
- "How do I budget?"
- "Should I invest or pay off debt?"
- "I want to increase my income"

### Health
- "I want to lose weight"
- "How do I build muscle?"
- "I have no energy"

### Life Planning
- "I want to plan my year"
- "I feel overwhelmed"
- "I don't know what to prioritize"

---

## Tips for Best Results

### 1. Be Specific
- ❌ "I want to be healthier"
- ✅ "I want to lose 15 lbs in 3 months"

### 2. Share Context
The more the agents know about your situation, the better they can help.

### 3. Use Debate Mode
When you're torn between options, ask for a debate:
```
You: "/debate Should I buy a house or keep renting?"
```

### 4. Check Your Status
Every few days, type `/status` to see your Context Object and stay on track.

### 5. Let Agents Guide You
If you're unsure, just say what's on your mind. The Orchestrator will figure out which agent to bring in.

---

## Troubleshooting

### "The LLM isn't following the agent structure"
- Make sure you uploaded ALL the files
- Try typing `/init` again
- Use ChatGPT Plus or Gemini Advanced (free versions have limited context)

### "It forgot my goal from last session"
- Copy the Context Object at the end of your session
- Paste it at the start of your next session
- Or just tell the Orchestrator: "Last time we were working on [goal]"

### "I want to change an agent's behavior"
- Edit the agent's `.md` file
- Re-upload to your LLM
- The changes will take effect immediately

---

## Next Steps

1. **Set your first goal** - What's one thing you want to achieve?
2. **Let the agents guide you** - They'll ask questions and create a plan
3. **Take action** - Follow the tasks the Activator gives you
4. **Review and adjust** - Use the Debriefer to learn and improve

---

**Ready? Upload the LifeOS folder and type `/init` to begin!**
