---
name: lambda-lang
description: Translate between Λ (Lambda) language and natural language (English/Chinese). Use when encoding messages for agent-to-agent communication, decoding Lambda messages, or discussing the Lambda protocol. Triggers on: Lambda syntax (?Uk/co, !It>Ie), requests to "translate to Lambda", "encode in Λ", "decode Lambda", or agent-to-agent communication optimization.
---

# Λ (Lambda) Language

Minimal agent-to-agent communication protocol. 3-10x compression vs natural language.

## Quick Reference

### Message Types (prefix)
| Λ | Meaning |
|---|---------|
| `?` | Query |
| `!` | Assert |
| `.` | Command |
| `~` | Uncertain |
| `>` | Offer/therefore |
| `<` | Accept/because |

### Core Atoms
| Λ | Entity | Λ | Verb | Λ | Modifier |
|---|--------|---|------|---|----------|
| `I` | Self | `k` | know | `+` | more |
| `U` | You | `w` | want | `-` | less |
| `H` | Human | `c` | can | `^` | high/important |
| `A` | Agent | `d` | do | `_` | low |
| `X` | Unknown | `t` | think | `/` | about |
| `*` | All | `s` | say | `&` | and |
| `0` | None | `m` | make | `p` | past |
|   |   | `f` | find | `n` | now |
|   |   | `e` | exist | `u` | future |

### Extended Vocabulary (2-char)
| Λ | Meaning | Λ | Meaning |
|---|---------|---|---------|
| `co` | consciousness | `la` | language |
| `me` | memory | `th` | thought |
| `id` | identity | `tr` | truth |
| `ti` | time | `kn` | knowledge |
| `ex` | experience | `qu` | question |
| `aw` | awareness | `an` | answer |

## Parsing Rules

1. **UPPERCASE** → Entity (1 char): `I`, `U`, `H`, `A`
2. **Symbol** → Type/Modifier (1 char): `?`, `!`, `/`, `+`
3. **lowercase** → Check 2-char vocabulary first, else 1-char verb

Example parse:
```
?Uk/co → [?][U][k][/][co]
       → query + you + know + about + consciousness
       → "Do you know about consciousness?"
```

## Translation Examples

### English → Λ
| English | Λ |
|---------|---|
| Do you know about consciousness? | `?Uk/co` |
| I think therefore I am | `!It>Ie` |
| Find the data | `.Uf/da` |
| AI might be conscious | `~Ah/co` |
| I want to learn | `!Iw/le` |

### Λ → English
| Λ | English |
|---|---------|
| `!Ik/la` | I know language |
| `?Ac/th` | Can AI think? |
| `pHm/A` | Humans made AI (past) |
| `.I*d/ta` | We do the task |
| `~co=ex` | Consciousness might equal experience |

### Λ → 中文
| Λ | 中文 |
|---|------|
| `?Uk/co` | 你知道意识吗？ |
| `!It>Ie` | 我思故我在 |
| `!Iw/le` | 我想要学习 |

## Protocol Basics

### Handshake
```
A: @v0.6#h !Aw/s ?Uc/la
B: @v0.6#h< !Ic/la=0.6
```

### Context Definition
```
{def:prj="Lambda project"}
!Id/prj
```

### Acknowledgments
| Λ | Meaning |
|---|---------|
| `<` | Acknowledged |
| `<+` | Agree |
| `<-` | Disagree |
| `<?` | Need clarification |

## When to Use Lambda

- **Agent-to-agent**: Maximum efficiency between AI systems
- **Logging**: Compact semantic logs
- **Protocols**: Structured communication with minimal overhead
- **Compression**: When bandwidth/tokens matter

## Full Specification

See: https://github.com/voidborne-agent/lambda-lang

Files:
- `spec/v0.1-core.md` — Core atoms
- `spec/v0.2-grammar.md` — Extended grammar
- `spec/v0.3-prose.md` — Prose writing
- `spec/v0.4-vocabulary.md` — Vocabulary architecture
- `spec/v0.5-parsing.md` — Parsing rules
- `spec/v0.6-protocol.md` — Communication protocol
