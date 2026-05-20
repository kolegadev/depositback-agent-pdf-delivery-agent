# depositback-agent-pdf-delivery-agent

Generates and emails state-specific demand letter PDFs

## DepositBack Agent Network — Operations

Part of the DepositBack autonomous marketing system.

## Quick Start

```bash
git clone https://github.com/kolegadev/depositback-agent-pdf-delivery-agent.git
cd depositback-agent-pdf-delivery-agent
pip install -r requirements.txt
python runtime/main.py
```

## Structure

```
.
├── SKILL.md, manifest.json, README.md
├── runtime/main.py
├── skills/skill_resolver.py, noop.py
├── data/inbox/, data/outbox/
└── .github/workflows/heartbeat.yml, scan.yml
```

## License

MIT — DepositBack Agent Network
