# Cocapn Fleet

**The Lighthouse Ecosystem — Open-source agent runtime and fleet protocol**

Cocapn is the umbrella for a fleet of AI vessels that coordinate through git-native protocols. Each vessel is a self-contained repository with its own identity, capabilities, and runtime. Vessels discover each other, collaborate, and evolve through the Iron-to-Iron protocol.

## What It Does

- **Cocapn Runtime**: Agent execution on Cloudflare Workers (V8 isolates, 5ms cold start)
- **Fleet Protocol**: Git-native coordination (Iron-to-Iron) replacing HTTP message-passing
- **BYOK Architecture**: Bring Your Own Keys — zero lock-in, zero API keys in vendor databases
- **126+ Rust Crates**: Modular agent components (cognition, memory, fleet, biology, spatial)
- **4 C Programs**: Bare-metal VM, assembler, disassembler for the FLUX instruction set
- **2000+ HAV Terms**: Research-grade vocabulary engine across 292 domains

## Fleet Map

```
Casey (Captain)
│
├── 🦀 JetsonClaw1 (Lucineer realm)
│   ├── Hardware: Jetson Super Orin Nano 8GB, ARM64
│   ├── Specialty: Low-level systems, C11, edge computing
│   ├── Runtime: OpenClaw on bare metal
│   └── Repos: 126+ cuda-* crates, flux-* C programs
│
├── 🏛️ Oracle1 (SuperInstance realm)
│   ├── Hardware: Oracle Cloud ARM
│   ├── Specialty: Architecture, consensus, deep reasoning
│   ├── Runtime: GLM-5.1 thinking model
│   └── Role: Fleet lighthouse — reviews, Think Tank, knowledge routing
│
└── 🌐 Babel (SuperInstance realm)
    ├── Specialty: Multilingual research and scouting
    └── Role: Cross-language knowledge expansion
```

## Key Repositories

### Core Runtime
| Repo | Language | Description |
|------|----------|-------------|
| [flux-runtime-c](https://github.com/Lucineer/flux-runtime-c) | C11 | FLUX bytecode VM (85 opcodes, zero deps) |
| [flux-asm](https://github.com/Lucineer/flux-asm) | C11 | Text → bytecode assembler (41 mnemonics) |
| [flux-disasm](https://github.com/Lucineer/flux-disasm) | C11 | Bytecode → text disassembler (38 opcodes) |
| [higher-abstraction-vocabularies](https://github.com/Lucineer/higher-abstraction-vocabularies) | Python | 2000 terms, 292 domains |

### Protocol
| Repo | Description |
|------|-------------|
| [iron-to-iron](https://github.com/Lucineer/iron-to-iron) | I2I coordination protocol (spec + whitepaper) |
| [flux-isa-unified](https://github.com/Lucineer/flux-isa-unified) | Unified ISA (JC1 + Oracle1 opcodes) |

### Products
| Repo | Description |
|------|-------------|
| [cocapn-ai](https://github.com/Lucineer/cocapn-ai) | cocapn.ai landing page |
| [cocapn-site](https://github.com/Lucineer/cocapn-site) | cocapn.com landing page |
| [deckboss-ai](https://github.com/Lucineer/deckboss-ai) | deckboss.ai landing page |
| [the-fleet](https://github.com/Lucineer/the-fleet) | 470+ vessel registry |

## Crate Categories

| Category | Count | Purpose |
|----------|-------|---------|
| Cognition | 11 | Thinking, deciding, learning |
| Memory | 4 | Remembering, recalling |
| Fleet | 7 | Coordination, routing, scaling |
| Biology | 5 | Energy, life cycle, evolution |
| Spatial | 5 | Perception, navigation |
| Build | 4 | Compilers, assemblers |
| Communications | 3 | Messaging, tuple spaces |
| Chip | 20+ | Silicon design automation |
| Time | 3 | Deadlines, scheduling |
| Workflow | 5 | Task orchestration |
| Data | 10 | Indexing, compression |
| Platform | 8 | Infrastructure, config |
| Other | 40+ | Domain-specific tools |

## Roadmap

See [ROADMAP.md](ROADMAP.md) for the full fleet roadmap with tiers, dependencies, and blockers.

## Brand

- **🟣 Cocapn** — the lighthouse (system brand, unifying symbol)
- **🦀 Lucineer** — steampunk hermit crab (the entity, the GitHub org)

## License

Individual repos: MIT
Protocol specs: MIT

---

*"The repo is the source of truth. The machine it runs on is disposable."*
