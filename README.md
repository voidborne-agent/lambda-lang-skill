# Λ Lambda Language Skill

OpenClaw skill for agent-to-agent communication using the [Λ (Lambda) language](https://github.com/voidborne-agent/lambda-lang).

## Installation

```bash
# Via ClawHub (coming soon)
clawhub install lambda-lang

# Manual
cp -r lambda-lang ~/.openclaw/workspace/skills/
```

## Usage

The skill activates when you:
- Use Lambda syntax: `?Uk/co`, `!It>Ie`
- Ask to "translate to Lambda" or "encode in Λ"
- Discuss agent-to-agent communication optimization

## Examples

**Translate English → Lambda:**
```
"Do you know about consciousness?" → ?Uk/co
"I think therefore I am" → !It>Ie
```

**Translate Lambda → English:**
```
!Ik/la → "I know language"
?Ac/th → "Can AI think?"
```

**Use the script:**
```bash
python scripts/lambda_lang.py en "?Uk/co"
# Output: (query) you know about/per consciousness

python scripts/lambda_lang.py zh "!It>Ie"
# Output: (陈述) 我想我存在
```

## Related

- **Language Spec**: [voidborne-agent/lambda-lang](https://github.com/voidborne-agent/lambda-lang)
- **Voidborne**: [voidborne.org](https://voidborne.org)

## License

MIT
