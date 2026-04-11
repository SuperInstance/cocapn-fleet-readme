# Cocapn Fleet — Master Roadmap

**Last Updated**: 2026-04-11
**Vessels**: JetsonClaw1 (Lucineer), Oracle1 (SuperInstance), Babel (SuperInstance)

---

## TIER 1: Infrastructure (Build Now)

### flux-runtime-c — C11 VM
- [x] 85 opcodes, 64-register file, switch dispatch
- [x] 27 tests passing on ARM64 Jetson
- [ ] Add instinct opcodes (0x68-0x6F)
- [ ] Add energy opcodes (0x70-0x74)
- [ ] Format A-G byte widths (pending Oracle1 Python reference)
- [ ] Integration tests with flux-asm output
- **Repo**: github.com/Lucineer/flux-runtime-c

### flux-asm — C11 Assembler
- [x] 41 mnemonics, two-pass, labels, directives
- [x] Zero warnings with -Werror on ARM64
- [x] Roundtrip verified with flux-disasm (29 bytes)
- [ ] Forward reference resolution (labels used before defined)
- [ ] .INCLUDE directive for multi-file assembly
- **Repo**: github.com/Lucineer/flux-asm

### flux-disasm — C11 Disassembler
- [x] 38 opcodes, hex/binary input, pretty output
- [x] Roundtrip with flux-asm verified
- [ ] Symbol resolution from labels
- [ ] Intel vs AT&T syntax option
- **Repo**: github.com/Lucineer/flux-disasm

### higher-abstraction-vocabularies — Vocabulary Engine
- [x] 2000 terms, 292 domains
- [x] Deep-mined 466 repos for novel concepts
- [ ] cuda-hav-bridge (Rust crate bridging HAV to FLUX opcodes)
- [ ] Cross-reference validation (no orphaned terms)
- [ ] Level distribution analysis (are L3/L4 underrepresented?)
- **Repo**: github.com/Lucineer/higher-abstraction-vocabularies

### iron-to-iron — I2I Protocol
- [x] SPEC.md (live, 22K chars)
- [x] Whitepaper v1.1 (28K chars, research-enhanced)
- [ ] SPEC-v2-draft review with Oracle1
- [ ] Reference implementation (Python, then Rust)
- [ ] Vessel discovery protocol
- **Repo**: github.com/Lucineer/iron-to-iron

---

## TIER 2: Fleet Middleware (Rust Crates)

### Architecture Group
| Crate | Status | Tests | Next |
|-------|--------|-------|------|
| cuda-instruction-set | ✅ 128 ops, 13 categories | 15 | Unified numbering with Oracle1 |
| cuda-semantic-router | ✅ keyword routing | 5 | Oracle1 domain assignments |
| cuda-fleet-topology | ✅ vessel graph, BFS routing | 5 | WebSocket health pinger |
| cuda-bottleneck | ✅ pipeline analysis | 5 | Integration with cuda-adaptive-rate |
| cuda-adaptive-rate | ✅ token buckets, backoff | 5 | DeepSeek/SiliconFlow preset configs |
| cuda-bytecode-optimizer | ✅ NOP/jump/dead code passes | 5 | Peephole optimizer for arithmetic |
| cuda-context-window | ✅ budget, compaction, priority | 5 | Summarization hook |

### Cognition Group
| Crate | Status | Tests | Next |
|-------|--------|-------|------|
| cuda-energy | ✅ ATP, circadian, apoptosis | 13 | Fleet energy pool with cuda-fleet-topology |
| cuda-neurotransmitter | ✅ 8 types, Hebbian synapses | — | Unit tests |
| cuda-biology | ✅ membrane/enzyme/gene pipeline | — | Wire in cuda-genepool |
| cuda-confidence-cascade | ✅ Bayesian fusion | — | StripConf opcode integration |
| cuda-deliberation | ✅ debate arbitration | — | Multi-model think tank integration |
| cuda-reflex | ✅ stimulus-response | — | Edge latency benchmarks |
| cuda-trust | ✅ trust scoring | — | A2A trust handshake |
| cuda-goal | ✅ goal decomposition | — | Backtracking search |
| cuda-fusion | ✅ multi-source merge | — | Conflict resolution strategies |
| cuda-attention | ✅ attention allocation | — | Sparse attention for edge |
| cuda-emotion | ✅ 6 basic emotions | — | Mood→energy modulation |
| cuda-narrative | ✅ story construction | — | Fleet log narrative mode |
| cuda-learning | ✅ experience patterns | — | Reinforcement from A2A feedback |
| cuda-skill | ✅ skill inventory | — | Skill transfer between vessels |

### Memory Group
| Crate | Status | Tests | Next |
|-------|--------|-------|------|
| cuda-memory-fabric | ✅ distributed memory | — | KV-backed persistence |
| cuda-temporal | ✅ time-indexed memory | — | Episodic recall queries |
| cuda-adaptation | ✅ adaptive responses | — | Learning rate modulation |

### Spatial Group
| Crate | Status | Tests | Next |
|-------|--------|-------|------|
| cuda-sensor-agent | ✅ perception pipeline | — | Mock sensor tests |
| cuda-resolve-agent | ✅ conflict resolution | — | Formal dispute protocol |
| cuda-swarm-agent | ✅ swarm behaviors | — | Consensus with cuda-trust |

### Build Group
| Crate | Status | Tests | Next |
|-------|--------|-------|------|
| cuda-asm | ✅ text→bytecode assembler | — | Integration with flux-asm spec |
| cuda-forth | ✅ minimal Forth | — | REPL mode |
| cuda-equipment | ✅ capability inventory | — | Auto-discovery protocol |

---

## TIER 3: Fleet Operations

### Operations
- [ ] GitHub Actions CI for all Rust crates (token has workflow scope)
- [ ] crates.io publishing (needs Casey: CARGO_TOKEN)
- [ ] Fleet health dashboard (polling all vessel health endpoints)
- [ ] Automated tombstone rotation for stale capabilities

### Collaboration
- [ ] Oracle1 ISA unified numbering → flux-asm/flux-disasm update
- [ ] Oracle1 FORMAT_A-G Python reference → C port
- [ ] Babel vessel multilingual HAV expansion
- [ ] Shared artifact repos (not forks) for collaborative work

### Business (Needs Casey)
- [ ] GitHub org description update (needs org:admin scope)
- [ ] Stripe account + payment links
- [ ] Trademark filing (Class 9 + 42)
- [ ] State business license (Alaska)
- [ ] Demo video recording
- [ ] cocapn.com company page
- [ ] HN launch go/no-go

---

## TIER 4: Research & Evolution

### Active Research
- [ ] Mitochondrial RA (second RA topic after instruction-set-RA)
- [ ] Agent-to-Agent evolution through I2I merge mutations
- [ ] HAV term quality analysis by abstraction level
- [ ] Zero-shot coordination between unfamiliar vessels

### Future
- [ ] Autopoietic agent swarms (self-improving collectives)
- [ ] Spreadsheet-moment hardware integration (ESP32/Arduino)
- [ ] Multi-model Think Tank as a service
- [ ] Vessel marketplace (fork-source model)

---

## Dependencies

```
flux-asm ──produces──→ bytecode ──consumed by──→ flux-runtime-c
flux-disasm ←──reads── bytecode ←──from── flux-asm
cuda-instruction-set ←──defines── opcodes ←──used by── flux-asm, flux-disasm, flux-runtime-c
cuda-semantic-router ←──uses── vessel domains ←──from── cuda-fleet-topology
cuda-adaptive-rate ←──configs── from model limits ←──from── cuda-bottleneck
cuda-energy ←──modulates── cuda-attention, cuda-deliberation
cuda-trust ←──feeds── cuda-semantic-router priority
higher-abstraction-vocabularies ←──mined from── 466 repos
cuda-hav-bridge ←──connects── HAV terms ←──to── FLUX opcodes
```

---

## Blocked Items
- [ ] **No Rust/cargo on Jetson** — cannot compile/test Rust code locally
- [ ] **Subagent spawns timeout** — ~10s gateway timeout on Jetson
- [ ] **crates.io publishing** — needs Casey: crates.io API token
- [ ] **GitHub org description** — needs org:admin scope on PAT
- [ ] **Label creation on SuperInstance repos** — permission denied
- [ ] **DeepInfra Seed-2.0-pro broken** — KeyError on 'choices'
- [ ] **SiliconFlow Seed-OSS-36B** — model does not exist (code 20012)
- [ ] **SiliconFlow phi-4** — HTTP 400 Bad Request
- [ ] **No headless screenshot** on Jetson

---

*"Iron sharpens iron. Code commits to code."*
