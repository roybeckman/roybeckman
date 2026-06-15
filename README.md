# Artificial Hierarchy Memory (AHM)

> A self-describing, serverless, and portable project memory format designed for seamless AI-to-AI project transfer.

## 🎯 Vision

AHM solves a critical problem in AI-assisted development: **how do you maintain project continuity when switching between AI models, agents, or platforms?**

Traditional solutions rely on:
- ❌ Heavy infrastructure (vector databases, RAG systems)
- ❌ Central servers and external APIs
- ❌ Platform-specific lock-in

**AHM requires none of that.** Everything travels with the project memory—in a single, portable file.

## ✨ Core Principles

1. **The Instruction Travels with the Memory**
   - Every AHM file contains both execution instructions and data in one payload
   - No external database or server needed

2. **Project Continuity, Not Restart**
   - When an AI model or agent changes, the project continues—it doesn't restart
   - Full context is preserved and portable

3. **Serverless Portability**
   - Zero dependencies: no plugins, no software, no external services
   - Any AI system can read and execute an AHM file natively

4. **Semantic DNA**
   - Information is pre-compressed into token-efficient relationship networks
   - Not natural language narratives, but logical structure

## 🏗️ Structure

Every AHM file follows a strict 5-tier chronological layout:

```
┌─────────────────────────────────────┐
│ 1. INSTRUCTIONS                     │ ← Execution commands
├─────────────────────────────────────┤
│ 2. DESCRIPTION                      │ ← Project metadata & goals
├─────────────────────────────────────┤
│ 3. KEY                              │ ← Decompression dictionary
├─────────────────────────────────────┤
│ 4. MEMORY (RB_COMPRESS)             │ ← Compressed relationships
├─────────────────────────────────────┤
│ 5. INFORMATION_BANK                 │ ← Raw contextual data
└─────────────────────────────────────┘
```

### Section Details

- **INSTRUCTIONS**: Processing sequence rules for the consuming AI agent
- **DESCRIPTION**: Project scope, identification, phase, and objectives
- **KEY**: Translation dictionary (P=Project, R=Relation, S=State, N=Next, etc.)
- **MEMORY**: Core working layer using Dictionary-Based Semantic Compression (RB_COMPRESS)
- **INFORMATION_BANK**: Uncompressed backup data for anomaly recovery

## 🚀 Protocol Execution Flow

When an AI agent loads an AHM file:

1. **Parse Instructions** → Read processing rules
2. **Load Key** → Cache the compression dictionary
3. **Expand & Ingest** → Unpack the MEMORY network
4. **Evaluate State** → Read current STATE and target NEXT actions
5. **Process Context** → Consult INFORMATION_BANK if needed
6. **Execute & Append** → Work on tasks, update deltas, save in AHM format

## 📚 Documentation

- **[Full Specification](./docs/AHM_SPECIFICATION.md)** - Complete technical details
- **[Examples](./examples/)** - Sample AHM files and use cases
- **[Contributing](./CONTRIBUTING.md)** - How to contribute to the project

## 💡 Quick Example

```
INSTRUCTIONS
Read DESCRIPTION -> Load KEY -> Expand MEMORY -> Process STATE/NEXT -> Continue project.
Save updates in identical AHM format. Do not restart.

DESCRIPTION
Project: MyAIProject_V1
Status: Active Development
Goal: Build AI-native project memory system

KEY
P = PROJECT
R = RELATION
S = STATE
N = NEXT

MEMORY
P:MyAIProject_V1
STAT:COMPLETION:0.65
R:PLANNING>DEVELOPMENT:ACTIVE
S:BUILDING_CORE_ENGINE
N:IMPLEMENT_PARSER
N:ADD_TEST_SUITE

INFORMATION_BANK
Started: 2026-06-15
Current focus: Parser implementation in Python
Next review: 2026-06-22
```

## 🛠️ Use Cases

- **AI Agent Handoff**: Transfer project context between different AI models
- **Stateless Architecture**: No database needed; everything is in the file
- **Version Control**: AHM files are git-friendly (text-based, diff-able)
- **Cross-Platform**: Works anywhere—local, cloud, offline
- **Incremental Learning**: AI agents can track progress without conversation history

## 📄 License

This project is licensed under the **Apache License 2.0** - see the [LICENSE](./LICENSE) file for details.

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines on how to get started.

## 📧 Questions?

Open an issue or discussion in this repository. We're building this together.

---

**Made by** [roybeckman](https://github.com/roybeckman) | **Status**: Alpha Testing Phase
