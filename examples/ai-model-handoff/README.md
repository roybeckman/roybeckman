# AI Model Handoff Example

## Overview

This example demonstrates how AHM enables seamless project transfer between different AI models or agents **without losing context or requiring a restart**.

## Scenario

A data pipeline project has been in development by GPT-4:
- ✅ Architecture designed
- ✅ Core ingestion layer implemented  
- ⚠️ Validation layer in progress
- ❌ Tests incomplete

**Now Claude is taking over** to continue the work.

## Key Features Demonstrated

### 1. **Clear Handoff Instructions**
The INSTRUCTIONS tier tells Claude exactly how to resume:
```
Read DESCRIPTION -> Load KEY -> Expand MEMORY -> Process STATE/NEXT.
Continue project without restarting.
```

### 2. **Complete State Snapshot**
MEMORY captures:
- Current completion: 70%
- Active tasks with priorities (γ values)
- Quality metrics (STAT)
- Dependencies and relationships (R entries)

### 3. **Rich Context** 
INFORMATION_BANK provides:
- What GPT-4 completed
- What Claude needs to do
- File locations and setup steps
- Known issues and bugs
- Current branch and test status

### 4. **Priority & Momentum Tracking**
```
N:COMPLETE_VALIDATION_LAYER γ:0.95 δ:+0.15
```
- **γ (gamma) = 0.95** → This is high priority
- **δ (delta) = +0.15** → Positive momentum (was at 0.55, now 0.70)

## How Claude Uses This File

**Step 1: Parse Instructions**
- Understand the handoff protocol

**Step 2: Load Key**
- Know that P=PROJECT, R=RELATION, etc.

**Step 3: Expand Memory**
- See that project is 70% complete
- Identify that VALIDATION_LAYER is next (highest priority)
- Understand architecture relationships

**Step 4: Evaluate State**
- Know current state: "FEATURE_DEVELOPMENT_70_PERCENT_COMPLETE"
- Know next state: Begin validation layer work

**Step 5: Read Information Bank**
- Get full context: what works, what doesn't
- Know file locations
- See setup instructions
- Find known issues

**Step 6: Execute**
- Clone repo, checkout feature/validation-layer
- Run tests to see current state
- Resume exactly where GPT-4 left off
- No restart needed!

## Benefits of This Approach

✅ **No Context Loss**: All information in one file
✅ **Clear Priorities**: γ values show what matters most
✅ **Momentum Tracking**: δ values show progress trajectory
✅ **Self-Contained**: No external databases needed
✅ **Portable**: Works anywhere, with any AI model
✅ **Version Control Friendly**: Git diffs show real changes

## Real-World Applications

- 🔄 **Team Handoffs**: Between human developers
- 🤖 **Model Switching**: Between different AI systems
- 🌍 **Global Teams**: Different timezones resuming work
- 📊 **Research**: Long-running studies with multiple contributors
- 🏢 **Enterprise**: Audit trail of all project states

## Try It Yourself

1. Read the `project.ahm` file
2. Follow the INSTRUCTIONS
3. Imagine you're Claude receiving this
4. Notice how you'd know exactly what to do next

## Variations

**Could also be used for:**
- GPT-4 → GPT-4 (same model, different session)
- Claude → GPT-4 (reverse handoff)
- Human Developer → AI Agent
- AI Agent → AI Agent
