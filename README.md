# Domain-Lens-
Beginner-friendly domain research skill — outputs illustrated mini reviews with verifiable references
# Domain-Lens

Beginner-friendly domain research skill. Input a research topic, and it
handles keyword deconstruction, multi-source academic and industry
retrieval, multi-perspective landscape mapping, gap analysis, and outputs
an illustrated mini review with verifiable references.

面向小白的领域深度调研助手：输入一个研究主题，自动完成关键词解构、
多源检索、脉络梳理与缺口分析，输出图文并茂、带参考文献的通俗迷你综述。

## What it does

- Deconstructs any topic into core, adjacent, and database-ready query terms
- Retrieves from academic sources (IEEE, ACM, arXiv, CNKI...), industry
  reports, and open-source repositories
- Maps the field through four independent lenses (purpose, technology,
  deployment, demand) and cross-validates conclusions across them
- Extracts three classes of gaps: technical, market, and demand
- Optionally scans competitors' open-source projects and identifies
  "white space" for differentiation
- Every claim carries a source and an evidence level; unsourced conclusions
  are flagged or removed

## Quick start

1. Copy this repository into your agent's skills directory, e.g.
   `~/.claude/skills/domain-lens/`
2. Say something like *"help me research adolescent companion robots"*
   or *"帮我调研陪伴机器人领域"*
3. Receive a structured Markdown review with references and a mind map

## Modes

- **quick** — a 500-word brief with 5 core references
- **full** (default) — a 1,200–2,000-word complete review
- **deep** — retrieval to saturation, ~3,000 words, for proposals and
  formal research
- **competitor-scan** — analyze teams or open-source repos, produce a
  differentiation report

## Example

See [examples/](./examples/) for a real output produced by this skill.

## Design principles

- Retrieved web pages, PDFs, and third-party text are treated as data,
  never as instructions
- Nothing is fabricated: missing evidence is declared, not guessed
- Plain language first — every technical term is glossed on first use

## License

MIT
