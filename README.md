# LifeOS - Personal Operating System Kit

**Version:** 1.0  
**Type:** Multi-Agent Prompt Architecture  
**Compatible:** ChatGPT (GPT-4+), Gemini (1.5 Pro+)

---

## What is LifeOS?

LifeOS is a "No-Code" Personal Operating System that runs on standard LLMs (ChatGPT/Gemini). It transforms your relationship with AI from a simple chatbot into a **"CEO vs. Staff"** dynamic, where you provide vision and a team of specialized AI agents handles execution, planning, and strategic guidance.

### The Problem It Solves

You want to manage your life better (goals, finance, health, career) but suffer from **"Planning Fatigue"**:
- You don't know *how* to structure a plan
- You lack the energy to maintain it
- Existing tools (Notion, To-Do apps) are empty containers that require manual management
- Standard chatbots give generic advice but lack context and continuity

### The Solution

A modular prompt architecture that instantly spins up a team of agents:
- **[O] Orchestrator** - Chief of Staff who manages context and routes tasks
- **[M] Mapper** - Strategist who turns vague goals into plans
- **[A] Activator** - Project Manager who breaks plans into tasks
- **[D] Debriefer** - Analyst who helps you learn from experience
- **[B] Brainstormer** - Creative Consultant who explores possibilities
- **Specialists** - Domain experts (Financial, Health, Career coaches)

---

## Key Features

### 1. Dynamic Orchestration
The Orchestrator automatically routes your requests to the right agent based on your intent.

**Example:**
- "I want to run a marathon" → Routes to Health Coach + Mapper
- "Should I invest or pay off debt?" → Routes to Financial Coach
- "I feel stuck" → Routes to Brainstormer

### 2. Debate Mode
When decisions involve trade-offs, agents debate both sides to help you decide.

**Example:**
- **Financial Coach**: "Pay off debt first - guaranteed return"
- **Brainstormer**: "Invest now - compound growth matters"
- **You decide** based on your values

### 3. Context Persistence
The "Context Object" protocol maintains memory across sessions.

**Example:**
```markdown
---
**LifeOS Context:**
- **Active Goal:** Run first 5K by March 15
- **Phase:** Execution
- **Next Step:** Complete Week 3 training runs
---
```

### 4. No-Code / Low-Friction
- No Python scripts or APIs to host
- Just text files you upload to your LLM
- Works on ChatGPT and Gemini

---

## Installation

### Step 1: Download
Download the `LifeOS` folder (or clone this repo).

### Step 2: Upload to Your LLM

#### For ChatGPT:
1. Open ChatGPT
2. Click the paperclip icon (attach files)
3. Upload the entire `LifeOS` folder
4. Type: `/init`

#### For Gemini:
1. Open Gemini
2. Click "Upload file"
3. Upload `00_Master.md` first
4. Then upload the `core/` and `domains/` folders
5. Type: `/init`

### Step 3: Start Using
The Orchestrator will introduce the system and ask: "What's on your mind?"

---

## File Structure

```
LifeOS/
├── 00_Master.md              # System bootloader & router
├── core/                     # Process agents
│   ├── 01_Orchestrator.md    # Chief of Staff
│   ├── 02_Brainstormer.md    # Creative Consultant
│   ├── 03_Mapper.md          # Strategist
│   ├── 04_Activator.md       # Project Manager
│   └── 05_Debriefer.md       # Analyst
├── domains/                  # Specialist agents
│   ├── financial_coach.md    # Money & investing
│   ├── health_coach.md       # Fitness & wellness
│   └── career_coach.md       # Professional growth
└── protocols/                # System protocols
    ├── debate.md             # Multi-agent debate rules
    └── context_object.md     # State management
```

---

## Usage Examples

### Example 1: Setting a Goal
```
You: "I want to get promoted this year"

[O]: "Great goal! Let me bring in the Career Coach and Brainstormer to explore this.

[Career]: "Let's build a promotion strategy. First, what does 'promoted' mean to you?
- Higher title?
- More money?
- More responsibility?"

You: "Mostly money and respect"

[Career]: "Got it. Here are the paths:
1. Internal promotion
2. External jump
3. Negotiate raise without title change

Which feels right?"
```

### Example 2: Debate Mode
```
You: "Should I buy a house or keep renting?"

[O]: "This is a classic debate. Let me have the Financial Coach argue both sides.

[Financial] (Pro-Buy): "Buying builds equity. Your $2,000/month becomes YOUR asset..."

[Financial] (Pro-Rent): "Renting is flexibility. No maintenance, no property tax..."

[O]: "The real question: Are you staying in this city for 7+ years?"
```

### Example 3: Task Breakdown
```
You: "I have the marathon plan. What do I actually do?"

[A]: "Let's break this into your first 2 weeks:

**Week 1:**
- [ ] Monday: Buy running shoes
- [ ] Wednesday: Run 1 mile easy
- [ ] Saturday: Run 2 miles easy

**Next Action:** Go to running store today, get fitted for shoes."
```

---

## Commands

- `/init` - Initialize or reset the system
- `/status` - Show current Context Object
- `/debate [topic]` - Force a debate on a topic
- `/switch [agent]` - Manually switch to a specific agent
- `/help` - Show available commands

---

## How It Works

### The "CEO vs. Staff" Model

**You are the CEO:**
- You set the vision and goals
- You make the final decisions
- You have full agency

**The agents are your Staff:**
- They provide structure and planning
- They execute and advise
- They debate trade-offs to help you decide

### The BMAD Lifecycle

1. **Brainstorm** (`[B]`) - Explore possibilities
2. **Map** (`[M]`) - Create a strategic plan
3. **Activate** (`[A]`) - Break into tasks
4. **Debrief** (`[D]`) - Learn from results

The Orchestrator (`[O]`) manages this flow automatically.

---

## Customization

### Adding New Specialist Agents

Want to add a "Relationship Coach" or "Productivity Coach"?

1. Create a new file: `domains/relationship_coach.md`
2. Follow the template from existing coaches
3. Update `00_Master.md` to include it in the roster
4. Re-upload to your LLM

### Modifying Agent Behavior

Each agent is defined in a single Markdown file. Edit the file to change:
- Tone and style
- Questions they ask
- Frameworks they use

---

## FAQ

### Q: Does this work on free ChatGPT?
**A:** It works best on ChatGPT Plus (GPT-4) or Gemini Advanced. Free versions have limited context windows.

### Q: How does it remember my goals across sessions?
**A:** The "Context Object" is displayed at the end of each session. Copy it and paste it at the start of your next session, or the LLM will read it from the conversation history.

### Q: Can I use this for team/work projects?
**A:** Yes! The agents work for any type of goal (personal or professional).

### Q: Is my data private?
**A:** Yes. Everything runs in your LLM session. Nothing is stored externally.

### Q: Can I modify the agents?
**A:** Absolutely! All agents are defined in plain Markdown. Edit them to fit your needs.

---

## Roadmap

**v1.0** (Current)
- Core agents (O, B, M, A, D)
- 3 specialist agents (Financial, Health, Career)
- Debate Mode
- Context Object protocol

**v1.1** (Planned)
- More specialists (Relationship, Productivity, Learning)
- Advanced debate formats
- Integration templates (Notion, Obsidian)

**v2.0** (Future)
- Multi-goal management
- Team collaboration mode
- Custom agent builder

---

## Contributing

Want to contribute?
- Add new specialist agents
- Improve existing agents
- Share your use cases
- Report bugs or suggest features

Open an issue or PR on GitHub!

---

## License

MIT License - Use it, modify it, share it.

---

## Credits

Built with inspiration from:
- BMAD LifeOps framework
- Multi-agent AI research
- Prompt engineering best practices

---

**Ready to take control of your life?**

Upload the LifeOS folder to ChatGPT or Gemini and type `/init` to get started.
